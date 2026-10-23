# NoSQL databases

“NoSQL” is a broad label for databases that are not primarily organized as traditional relational tables, or that provide additional data models and scaling approaches. It does not mean that such databases cannot use query languages.

Common categories include:

- **Document databases:** store records as documents, often JSON-like.
- **Key-value stores:** retrieve a value using a key.
- **Wide-column databases:** organize data for large distributed workloads.
- **Graph databases:** represent entities and their relationships as a graph.

These models can fit particular data shapes and access patterns well. A document database may make it convenient to store a whole profile together, while a graph database may be useful for exploring many relationships.

NoSQL is not automatically faster or easier to scale, and it does not automatically eliminate schemas. Applications still need to decide what data looks like, how to validate it, and how to handle consistency. Choose based on query patterns, operational needs, and correctness requirements—not fashion. Compare with [SQL databases](sql.md), and read about [indexes](indexes.md) and [transactions](transactions.md).

## Curiosity questions

70. What is the difference between SQL and NoSQL?

## Explanations guided by the seven questions

### 70. What is the difference between SQL and NoSQL?

Different data models suit different structures and access patterns. SQL commonly describes relational databases; NoSQL covers several other models. Relational systems use tables and relations; NoSQL may use documents, keys, graphs, or columns. Both are used in local, server, and cloud deployments. Choose based on queries, consistency needs, scale, and operational fit. Teams select and operate the database that fits their product. Either model can be a poor fit when chosen without understanding data access.
