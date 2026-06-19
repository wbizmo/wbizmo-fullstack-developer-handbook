# Lesson 04: SQL Fundamentals

## Learning Objectives

By the end of this lesson you should be able to:

- Understand SQL.
- Create tables.
- Insert data.
- Query data.
- Update data.
- Delete data.

## What Is SQL?

SQL means:

    Structured Query Language

SQL is used to communicate with relational databases.

Examples:

- PostgreSQL
- MySQL
- SQLite
- MariaDB

## Creating Tables

Example:

    CREATE TABLE users (
        id SERIAL PRIMARY KEY,
        name VARCHAR(255),
        email VARCHAR(255)
    );

Creates:

    users

table.

## Inserting Data

Example:

    INSERT INTO users (
        name,
        email
    )
    VALUES (
        'Ada',
        'ada@email.com'
    );

## Reading Data

Example:

    SELECT *
    FROM users;

Output:

All users.

## Selecting Specific Columns

    SELECT
        name,
        email
    FROM users;

## Updating Data

Example:

    UPDATE users
    SET email =
        'new@email.com'
    WHERE id = 1;

## Deleting Data

Example:

    DELETE FROM users
    WHERE id = 1;

## CRUD Mapping

Create:

    INSERT

Read:

    SELECT

Update:

    UPDATE

Delete:

    DELETE

## Real World Example

Books:

    CREATE TABLE books (
        id SERIAL PRIMARY KEY,
        title VARCHAR(255),
        author VARCHAR(255)
    );

Insert:

    INSERT INTO books (
        title,
        author
    )
    VALUES (
        'Node.js Guide',
        'Ada'
    );

Query:

    SELECT *
    FROM books;

## Mini Project

Create:

- users table
- books table

Insert:

- 3 users
- 3 books

Query all records.

## Exercises

1. Create a table.
2. Insert records.
3. Select records.
4. Update records.
5. Delete records.

## Summary

SQL provides commands for managing data.

The four most important operations are:

- INSERT
- SELECT
- UPDATE
- DELETE

## References

https://www.postgresql.org/docs/current/sql.html
