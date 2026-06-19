# Lesson 06: Joins and Multi-Table Queries

## Learning Objectives

By the end of this lesson you should be able to:

- Understand joins.
- Use INNER JOIN.
- Use LEFT JOIN.
- Query related data.
- Understand relationship traversal.

## Why Joins Exist

Data is split across tables.

Example:

authors

| id | name |

books

| id | title | author_id |

To combine information:

Use joins.

## INNER JOIN

Returns matching records.

Example:

    SELECT
        books.title,
        authors.name
    FROM books
    INNER JOIN authors
        ON books.author_id =
           authors.id;

Output:

Book title and author name.

## LEFT JOIN

Returns all rows from the left table.

Example:

    SELECT
        authors.name,
        books.title
    FROM authors
    LEFT JOIN books
        ON books.author_id =
           authors.id;

Even authors without books appear.

## One-To-Many Example

Users

Orders

Query:

    SELECT
        users.name,
        orders.id
    FROM users
    INNER JOIN orders
        ON orders.user_id =
           users.id;

## Many-To-Many Example

Students

Courses

Enrollments

Join through:

    enrollments

## Library Database Example

Books

Authors

Categories

Borrowed Books

Users

All connected through joins.

## Multi Join Example

    SELECT
        books.title,
        authors.name,
        categories.name
    FROM books
    INNER JOIN authors
        ON books.author_id =
           authors.id
    INNER JOIN categories
        ON books.category_id =
           categories.id;

## Mini Project

Query:

- Books and authors
- Books and categories
- Users and borrowed books

## Exercises

1. Create INNER JOIN query.
2. Create LEFT JOIN query.
3. Query books and authors.
4. Query books and categories.
5. Explain one-to-many joins.

## Summary

Joins combine related data.

INNER JOIN returns matches.

LEFT JOIN preserves left-side records.

Joins are essential for relational databases.

## References

https://www.postgresql.org/docs/current/tutorial-join.html
