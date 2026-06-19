# Lesson 09: Real World Database Design Project

## Learning Objectives

By the end of this lesson you should be able to:

- Design a complete relational database.
- Create relationships.
- Apply indexing.
- Plan migrations.
- Think like a backend engineer.

## Project Overview

Build:

    Library Management Database

Tables:

- users
- authors
- categories
- books
- borrowed_books

## Requirements

Users can:

- Borrow books
- Return books

Books:

- Belong to authors
- Belong to categories

System must:

- Track borrowers
- Track inventory
- Track borrowing history

## Schema Design

users

    id
    name
    email

authors

    id
    name

categories

    id
    name

books

    id
    title
    author_id
    category_id

borrowed_books

    id
    user_id
    book_id
    borrowed_at
    returned_at

## Relationships

authors

    1 -> many books

categories

    1 -> many books

users

    many borrowed books

books

    many borrow records

## Recommended Indexes

users.email

books.title

borrowed_books.user_id

borrowed_books.book_id

## Migration Plan

Migration 1:

Create users.

Migration 2:

Create authors.

Migration 3:

Create categories.

Migration 4:

Create books.

Migration 5:

Create borrowed_books.

## Architecture Thinking

Questions:

- How do we find overdue books?
- How do we find most borrowed books?
- How do we find active borrowers?

These become SQL queries.

## Exercises

1. Draw ER diagram.
2. Define relationships.
3. Define indexes.
4. Write migration order.
5. Design overdue books query.

## Summary

Database design affects application performance, maintainability, and scalability.

Good schemas make backend systems easier to build.

## References

https://www.postgresql.org/docs/current/
