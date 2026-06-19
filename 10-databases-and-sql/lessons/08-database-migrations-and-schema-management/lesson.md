# Lesson 08: Database Migrations and Schema Management

## Learning Objectives

By the end of this lesson you should be able to:

- Understand migrations.
- Understand schema evolution.
- Create migration files.
- Apply migrations.
- Roll back migrations.

## What Is A Migration?

A migration is a version-controlled database change.

Example:

Version 1:

    users

Version 2:

Add:

    phone_number

Migration records that change.

## Why Migrations Matter

Without migrations:

Nobody knows how the database changed.

With migrations:

Changes are reproducible.

## Example Migration

Create users:

    CREATE TABLE users (
        id SERIAL PRIMARY KEY,
        email VARCHAR(255)
    );

Later:

    ALTER TABLE users
    ADD COLUMN phone_number
    VARCHAR(50);

## Migration Workflow

Developer:

Creates migration.

Team:

Applies migration.

Database:

Updates schema.

## Rollbacks

Undo migration.

Example:

    ALTER TABLE users
    DROP COLUMN phone_number;

## Real World Tools

- Prisma Migrate
- Laravel Migrations
- Knex Migrations
- Sequelize Migrations

## Portfolio Examples

Used in:

- Covenant
- SyncGrid
- VaultBox
- inFlowForge

## Exercises

1. Explain migrations.
2. Create table migration.
3. Add column migration.
4. Create rollback migration.
5. Explain schema evolution.

## Summary

Migrations manage database changes safely.

Production systems rely heavily on migration workflows.

## References

https://www.prisma.io/docs/orm/prisma-migrate
