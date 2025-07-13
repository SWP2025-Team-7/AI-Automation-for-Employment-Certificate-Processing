# Automated Tests

## Unit tests

- Location: bot/tests/test_handlers
- Characteristics:
    - Isolated component testing
    - Mocked dependencies (database, services)
    - Fast execution (no external dependencies)
``` python
@pytest.mark.asyncio
async def test_start_handler(memory_storage, bot):
    message = AsyncMock() # Mocked data
    state = FSMContext( # FSM state
        storage=memory_storage,
        key=StorageKey(
            bot_id=bot.id,
            user_id=TEST_USER.id,
            chat_id=TEST_USER_CHAT.id,
        )
    )
    await start_handler(msg=message, state=state) #starting handler with mocked data
    assert await state.get_state() == StudentStates.start # checking
```

## Integrational tests

- Location: backend/test/test_users.py
- Characteristics:
    - Tests linking between services
    - Mocked dependencies (database, services)

```python
def test_get_nonexistent_user():
    app.dependency_overrides[get_repository(UsersRepository)] = lambda: mock_repo
    mock_repo = MagicMock() # Mocking data
    mock_repo.get_user_by_id = AsyncMock(return_value=None)

    client = TestClient(app)
    response = client.get("/users/9999")
    assert response.status_code == 404

```