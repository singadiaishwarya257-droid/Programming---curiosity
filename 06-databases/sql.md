# SQL databases

SQL (Structured Query Language) is used to define, query, and modify data in relational databases. A relational database organizes information into tables made of rows and columns, with relationships often represented by keys.

For example, a `books` table might have `id`, `title`, and `author` columns. A query can select matching rows:

```sql
SELECT title, author
FROM books
WHERE author = 'Ursula Le Guin';
```

A primary key identifies a row. A foreign key can connect a row to one in another table, helping preserve relationships. SQL databases often support transactions, constraints, and structured schemas.

Relational databases are useful when data has clear relationships and you need reliable queries or consistent updates. Good table design matters: duplicated information can become difficult to keep in sync.

SQL is a language; different database products implement it with variations. Some relational databases also support JSON and other flexible data. See [indexes](indexes.md) for faster lookups and [transactions](transactions.md) for reliable groups of changes.

## Curiosity questions

61. Why can't we simply store everything in Python variables?
62. Why do applications need databases?
63. What happens when you click “Save”?
64. Where does the data physically go?
65. What is a table?
66. What is a row?
67. What is a column?
68. Why do we need primary keys?

## Explanations guided by the seven questions

### 61. Why can't we simply store everything in Python variables?

Variables disappear with the process and are limited by available memory. They hold temporary in-memory state, not durable shared records. Databases persist data and provide querying, concurrency, and recovery mechanisms. Variables are in process memory; database data is on managed storage. Use variables for active computation and a database for durable application data. The application and database service manage their respective data. A process crash can erase unsaved variable state.

### 62. Why do applications need databases?

Applications often need durable, searchable, shared information. A database organizes and manages data with defined operations. It stores records, answers queries, and may enforce constraints and transactions. It runs locally, on a server, or as a managed cloud service. Use one when data must outlive a process or be shared reliably. Applications, administrators, and users interact with it through controlled access. Poor schema, backups, or access controls can cause loss or exposure.

### 63. What happens when you click “Save”?

The application needs to retain the change beyond the current interaction. The UI sends data to application logic, which validates and persists it. A request reaches a server, which may execute a database transaction. Data moves from the device through a service to database storage. Persistence follows validation and succeeds only after the required commit. UI, API, business logic, database, and storage participate. Failure should be reported; the UI should not claim success before confirmation.

### 64. Where does the data physically go?

Persistent data must survive process restarts and power loss. The database encodes records into files or storage blocks. It writes through OS and storage layers, often using logs and caches. On local disks, network storage, or provider-managed data centers. Durability depends on when writes are flushed and the database's guarantees. Database software, OS, storage hardware, and operators manage it. Backups and replication help recover from device failure, but must be tested.

### 65. What is a table?

Related records need a consistent structure for storage and querying. A relational table is a named set of rows described by columns. The schema defines columns, types, constraints, and relationships. It exists in a relational database's logical data model. Use tables when data fits a relational structure. Designers define schemas; applications query and update them. Poor table design can duplicate data or make changes error-prone.

### 66. What is a row?

Each individual record needs a place in a table. A row is one record with values for the table's columns. SQL inserts, selects, updates, and deletes rows. It is a logical record stored by the database. Rows represent entities or events in a relational model. Applications and users manipulate them through queries. Constraints can reject a row that violates data rules.

### 67. What is a column?

Records need named attributes with defined meaning. A column describes one attribute shared by rows in a table. Its name, type, and constraints define allowed values. It belongs to a table schema. Add a column when the data model requires a new attribute. Schema designers define it; queries read and write values. Changing a column can require data migration and application updates.

### 68. Why do we need primary keys?

Each row needs a reliable way to be uniquely identified. A primary key is a unique, non-null identifier for a table row. The database enforces uniqueness and can use the key for references. It is declared in the table schema. Use it whenever rows need stable identification or relationships. Schema designers choose it; the database enforces it. Unstable or duplicate identifiers make updates and relationships unreliable.
