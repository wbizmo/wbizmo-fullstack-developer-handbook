# Lesson 02: Relational vs Non-Relational Databases

## Learning Objectives

- Understand relational databases.
- Understand NoSQL databases.
- Compare strengths and weaknesses.
- Know when to use each.

## Relational Databases

Examples:

- PostgreSQL
- MySQL
- MariaDB
- SQLite

Data is stored in tables.

Example:

users

orders

products

Relationships connect tables.

## Non-Relational Databases

Examples:

- MongoDB
- Redis
- Cassandra

Data may be stored as:

- Documents
- Key-value pairs
- Graphs
- Wide-column records

## Relational Example

Users:

| id | name |
|----|------|
| 1 | Ada |

Orders:

| id | user_id |
|----|---------|
| 1 | 1 |

Relationship:

user_id -> users.id

## MongoDB Example

    {
      "_id": "1",
      "name": "Ada",
      "orders": [
        {
          "id": "101"
        }
      ]
    }

## Advantages Of SQL

- Strong consistency
- Relationships
- Powerful queries
- Mature tooling

## Advantages Of NoSQL

- Flexible structure
- Easy horizontal scaling
- Fast document storage

## When To Use SQL

Examples:

- ERP
- Finance
- Inventory
- Contracts
- Business systems

## When To Use NoSQL

Examples:

- Logs
- Analytics
- Flexible content
- Rapid prototyping

## Exercises

1. List SQL databases.
2. List NoSQL databases.
3. Compare SQL and NoSQL.
4. Explain relationships.
5. Explain document databases.

## Summary

SQL databases organize data into tables.

NoSQL databases use alternative storage models.

Both have valid use cases.

## References

https://www.mongodb.com/docs/

https://www.postgresql.org/docs/
