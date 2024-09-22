Here’s the `README.md` for your Todo List project:

---

# AddrX Todo List Module

## Vision

The AddrX Todo List aims to create a decentralized task management system on the Aptos blockchain. By leveraging the immutable nature of blockchain, users can track tasks, ensure task completion status transparency, and benefit from an event-driven system without relying on traditional centralized services. This decentralized task management ensures users own their data and can confidently trust the system without interference.

## Features

- **Create Task List**: Users can initialize their own to-do list on the blockchain.
- **Add Tasks**: Add tasks with a unique ID and description to the list.
- **Complete Tasks**: Mark tasks as complete, with the status securely updated on-chain.
- **Event-Driven Task Management**: Each task creation and completion triggers an event on the blockchain, ensuring transparency and traceability.
- **Task Counter**: Keeps track of the number of tasks created per user.
- **Immutable Records**: All tasks and their status updates are recorded immutably.

## Future Scope

In future iterations, we aim to introduce several features to enhance the functionality of the AddrX Todo List module:
- **Task Categories and Prioritization**: Allow users to categorize tasks (e.g., "Work," "Personal") and assign priority levels.
- **Task Due Dates**: Add due date functionality to help users manage deadlines effectively.
- **Shared Lists**: Enable collaborative task lists, allowing multiple users to add, complete, and manage tasks together.
- **Reminders and Notifications**: Implement a reminder system to notify users of upcoming tasks or overdue tasks via smart contract-triggered notifications.
- **Enhanced Security**: Introduce more granular permissions, enabling the management of who can add or modify tasks.

## Smart Contract Information

### Structs

- **`TodoList` Struct**: 
  - Holds a list of tasks in a table, along with an event handle for task creation, and a task counter.
  
- **`Task` Struct**: 
  - Represents an individual task, containing the task ID, the address of the creator, content (description), and completion status.

### Important Constants

- **`E_NOT_INITIALIZED`**: Thrown when trying to access a non-initialized task list.
- **`ETASK_DOESNT_EXIST`**: Thrown when trying to access or complete a task that doesn’t exist.
- **`ETASK_IS_COMPLETED`**: Thrown when attempting to complete a task that is already marked as complete.

### Core Functions

#### `create_list(account: &signer)`
- Initializes a new task list for the user and associates it with their account on-chain.

#### `create_task(account: &signer, content: String) acquires TodoList`
- Adds a new task to the user’s to-do list. The task is given a unique ID and an initial status of "not completed."

#### `complete_task(account: &signer, task_id: u64) acquires TodoList`
- Marks a task as completed. The task must exist, and it cannot already be completed.

### Test Cases

- **`test_flow(admin: signer)`**: Verifies the full lifecycle of the module, from creating a list to creating and completing tasks.
- **`account_can_not_update_task(admin: signer)`**: Verifies that an account without an initialized list cannot complete a task, throwing the appropriate error (`E_NOT_INITIALIZED`).

---

This module represents a step toward decentralized, transparent task management on the blockchain, providing security and accountability for users' personal and professional tasks. We look forward to expanding its features in the future!

--- 

### DEPLOYMENT
- ** contract link - https://explorer.aptoslabs.com/account/0xbfff0d917e8eeb80a06b4631ef8f1bfc2b6008ae4863bb275bb2435799fbae2e/modules/code/todolist?network=devnet
- ** address - 0xbfff0d917e8eeb80a06b4631ef8f1bfc2b6008ae4863bb275bb2435799fbae2e
