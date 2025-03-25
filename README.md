# Budget React App

This is a **Budget Management Application** built with **React** and **Redux Saga**. The project focuses on learning and implementing **Redux Saga** to handle side effects like API calls and asynchronous workflows in a Redux-based application.

## Features

- Add, update, and delete budget entries.
- Fetch and display detailed entry information.
- Manage asynchronous operations using Redux Saga.

## Redux Saga Highlights

- **Side Effect Management**: Handles API calls with `call` and `put`.
- **Concurrency**: Uses `takeEvery`, `takeLatest`, and `fork` for managing tasks.
- **Cancellation**: Implements `cancel` and `cancelled` for long-running tasks.
- **Example**: Fetching entries, adding entries, and deleting entries are all managed through sagas.

### Example: Deleting an Entry
```js
export function* deleteEntrySaga() {
  while (true) {
    const { payload } = yield take(entriesTypes.REMOVE_ENTRY);
    yield call(deleteEntrie, payload.id);
    yield put({ type: 'REMOVE_ENTRY_RESULT', payload: { id: payload.id } });
  }
}
```

## Learning Outcomes

This project helped me understand how to use **Redux Saga** for managing side effects, concurrency, and task cancellation in a scalable and maintainable way.
