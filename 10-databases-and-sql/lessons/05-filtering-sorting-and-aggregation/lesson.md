# Lesson 05: Filtering, Sorting and Aggregation

## Learning Objectives

By the end of this lesson you should be able to:

- Filter records.
- Sort records.
- Limit results.
- Count records.
- Aggregate data.

## Filtering With WHERE

Example:

    SELECT *
    FROM users
    WHERE id = 1;

Returns one user.

## Multiple Conditions

    SELECT *
    FROM users
    WHERE age > 18;

## AND

    SELECT *
    FROM users
    WHERE age > 18
    AND country = 'Nigeria';

## OR

    SELECT *
    FROM users
    WHERE country = 'Nigeria'
    OR country = 'Ghana';

## Sorting

Ascending:

    SELECT *
    FROM users
    ORDER BY name ASC;

Descending:

    SELECT *
    FROM users
    ORDER BY name DESC;

## Limiting Results

    SELECT *
    FROM users
    LIMIT 10;

Useful for pagination.

## Counting Records

    SELECT COUNT(*)
    FROM users;

## Summing Values

    SELECT SUM(amount)
    FROM transactions;

## Average Values

    SELECT AVG(amount)
    FROM transactions;

## Maximum Value

    SELECT MAX(amount)
    FROM transactions;

## Minimum Value

    SELECT MIN(amount)
    FROM transactions;

## Grouping

Example:

    SELECT country,
           COUNT(*)
    FROM users
    GROUP BY country;

## Real Example

Cashflowr:

Calculate:

- Total expenses
- Average expense
- Highest expense

Using aggregation.

## Mini Project

Create queries for:

- Total books
- Books per author
- Newest books
- Oldest books

## Exercises

1. Filter users.
2. Sort users.
3. Limit users.
4. Count users.
5. Group users by country.
6. Calculate averages.

## Summary

Filtering narrows results.

Sorting orders results.

Aggregation summarizes data.

## References

https://www.postgresql.org/docs/current/tutorial-select.html
