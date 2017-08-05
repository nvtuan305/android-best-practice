## Best practice for SQLite Database.
### [**SQLite Transaction**](http://www.sqlitetutorial.net/sqlite-transaction/)

**SQlite & ACID**

SQlite is a transactional database that all changes and queries are atomic, consistent, isolated, and durable (ACID). SQLite guarantees all the transactions are ACID compliant even if the transaction is interrupted by program crash, operation system dump, or power failure to the computer.

- Atomic: a transaction should be atomic. It means that a change cannot be broken down into smaller ones. When you commit a transaction, either entire the transaction is applied or not applied. It cannot be only part of the transaction to be applied .

- Consistent: a transaction must ensure to change the database from one valid state to another. When a transaction starts and executes statements to modify data, the database becomes inconsistent. However, when the transaction is committed or rolled back, it is important that the transaction must keep the database consistent.

- Isolation: a pending transaction must be isolated from other clients. When a client starts a transaction and executes the INSERT or UPDATE statement to change the data, those changes are only visible to the client, not other clients. On the other hand, the changes committed by other clients after the transaction started should not be visible to this client.

- Durable: if a transaction is successfully committed, the changes must be permanent in the database regardless of the condition such as power failure or program crash. On the contrary, if the program crash before the transaction is committed, the change should not be present.

### [**How to optimize SQLite 1?**](http://www.whoishostingthis.com/compare/sqlite/optimize/)
### [How to optimize SQLite 2?](https://stackoverflow.com/questions/1711631/improve-insert-per-second-performance-of-sqlite)

- Use transaction.
- Use a prepared Statement.
- PRAGMA synchronous = OFF (**risk**)
- PRAGMA journal_mode = MEMORY (**risk**)
- Using an In-Memory Database (**risk**)
- Only Index When You Really Need It
- Set PRAGMA cache_size, tempt_store = MEMORY
- Reorder WHERE conditions 
- Case Insensitive Indexes for LIKE
- Use the lastest version
