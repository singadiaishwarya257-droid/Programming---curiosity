# Database indexes

An index is an additional data structure that helps a database find rows without scanning every row in a table. It is similar to a book's index: instead of reading every page, you look up a topic and jump to the relevant pages.

If an application often searches books by title, an index on the `title` column may speed up that query:

```sql
CREATE INDEX books_title_idx ON books (title);
```

## Trade-offs

Indexes take storage and need to be updated when data changes. Too many indexes can slow down inserts and updates; an index on a column that is rarely queried may not be worth its cost. Indexes can also involve multiple columns or specialized structures depending on the database.

The database's query planner decides whether an index is useful for a particular query. An index does not guarantee a faster query, so use query plans and measurements to understand performance. Indexes complement good schema and queries; they do not replace them. See [SQL databases](sql.md) and [transactions](transactions.md).

## Curiosity questions

69. Why do we need indexes?

## Explanations guided by the seven questions

### 69. Why do we need indexes?

Searching every row can be slow as data grows. An index is an auxiliary structure that helps locate matching rows. The database traverses indexed keys and retrieves corresponding records. It is stored and maintained alongside database data. Add one for measured, frequent query patterns. Database designers choose indexes; the engine maintains them. Too many indexes consume storage and slow writes.
