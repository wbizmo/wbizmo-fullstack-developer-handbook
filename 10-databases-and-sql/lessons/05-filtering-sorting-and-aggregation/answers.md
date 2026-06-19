# Lesson 05 Answers

1. Filters records.
2. Sorts records.
3. Restricts result count.
4. Counts records.
5. Adds values.
6. Calculates average.
7. Largest value.
8. Smallest value.
9. Groups records.
10. Summarizes data.

## Mini Project Solution

    SELECT COUNT(*)
    FROM books;

    SELECT author,
           COUNT(*)
    FROM books
    GROUP BY author;

    SELECT *
    FROM books
    ORDER BY created_at DESC;
