# Lesson 07: Indexes and Performance Basics

## Learning Objectives

By the end of this lesson you should be able to:

- Understand database indexes.
- Explain why indexes exist.
- Create indexes.
- Understand query performance.
- Recognize indexing tradeoffs.

## Why Indexes Exist

Imagine a library with:

    1,000,000 books

Without an index:

You check every book.

With an index:

You jump directly to the correct section.

Databases work similarly.

## What Is An Index?

An index is a special data structure that helps databases find records faster.

Without index:

    Slow lookup

With index:

    Fast lookup

## Example

Table:

    users

Columns:

    id
    name
    email

Query:

    SELECT *
    FROM users
    WHERE email =
        'ada@email.com';

Email is a good indexing candidate.

## Creating Indexes

Example:

    CREATE INDEX
    idx_users_email
    ON users(email);

## Primary Keys Are Indexed

Example:

    id SERIAL PRIMARY KEY

Automatically creates an index.

## Good Index Candidates

- email
- username
- foreign keys
- frequently searched columns

## Bad Index Candidates

- Frequently changing values
- Columns rarely queried

## Index Tradeoffs

Indexes improve:

- Reads

Indexes slightly slow:

- Inserts
- Updates
- Deletes

Because indexes must be maintained.

## Real Example

VaultBox:

Search user by email.

SyncGrid:

Search API key.

inFlowForge:

Search workflow id.

Indexes improve these queries.

## Exercises

1. Explain index.
2. Create an email index.
3. List good index candidates.
4. List bad index candidates.
5. Explain tradeoffs.

## Summary

Indexes improve query performance.

Not every column should be indexed.

Proper indexing is critical for large applications.

## References

https://www.postgresql.org/docs/current/indexes.html
