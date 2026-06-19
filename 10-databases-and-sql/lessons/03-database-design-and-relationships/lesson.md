# Lesson 03: Database Design and Relationships

## Learning Objectives

By the end of this lesson you should be able to:

- Design tables.
- Create relationships.
- Understand primary keys.
- Understand foreign keys.
- Model real-world systems.

## Database Design

Good design prevents:

- Duplicate data
- Inconsistencies
- Poor performance

## Primary Keys

Primary keys uniquely identify records.

Example:

users

| id | name |
|----|------|
| 1 | Ada |

Primary key:

    id

## Foreign Keys

Foreign keys connect tables.

Users:

| id | name |
|----|------|
| 1 | Ada |

Orders:

| id | user_id |
|----|---------|
| 1 | 1 |

Foreign key:

    user_id

References:

    users.id

## Relationship Types

### One-To-One

User

Profile

One user → one profile

### One-To-Many

User

Orders

One user → many orders

### Many-To-Many

Students

Courses

Many students → many courses

## Library Project Design

Authors

| id | name |

Books

| id | title | author_id |

Relationship:

author_id → authors.id

## Borrowing System

Users

Books

Borrowed Books

Borrowed Books acts as a linking table.

## Mini Project

Design:

- users
- books
- authors
- categories

Define all relationships.

## Exercises

1. Define primary key.
2. Define foreign key.
3. Explain one-to-many.
4. Explain many-to-many.
5. Design a school database.

## Summary

Relationships connect tables.

Primary keys identify records.

Foreign keys create links.

Good database design improves scalability.

## References

https://www.postgresql.org/docs/current/ddl-constraints.html
