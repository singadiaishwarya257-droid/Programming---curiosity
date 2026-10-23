# Database transactions

A transaction groups database operations so they behave as one logical unit. If a transfer must subtract money from one account and add it to another, both changes should succeed together—or neither should be committed.

Transactions are often explained using ACID:

- **Atomicity:** the group is all-or-nothing.
- **Consistency:** rules and constraints remain satisfied.
- **Isolation:** concurrent transactions are controlled to avoid unwanted interference.
- **Durability:** committed changes survive failures according to the database's guarantees.

The exact isolation levels and guarantees vary between databases. Applications need to choose appropriate behavior and handle conflicts or failures.

Conceptually:

```text
BEGIN
  subtract from account A
  add to account B
COMMIT
```

If an operation fails, the application can roll back instead of leaving a partial transfer. Transactions are useful for related changes, but holding them open too long can reduce performance or block other work. Read [SQL databases](sql.md) for tables and [indexes](indexes.md) for query performance.

## Curiosity questions

What happens if two users try to modify the same database record at exactly the same time?

## Explanations guided by the seven questions

### Rabbit hole: What if two users modify the same database record at exactly the same time?

Concurrent changes can overwrite one another or violate business rules. The database must coordinate competing transactions. Isolation levels, locks, optimistic version checks, or serializable execution manage conflicts. Coordination occurs in the database engine and sometimes application logic. It matters whenever concurrent requests read or change overlapping data. Database transactions and application conflict handling participate. One operation may wait, fail, retry, or overwrite depending on the chosen policy.
