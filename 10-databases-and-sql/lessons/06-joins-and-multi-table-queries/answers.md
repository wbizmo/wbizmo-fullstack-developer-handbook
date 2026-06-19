# Lesson 06 Answers

1. Combining related tables.
2. To access related data.
3. Matching records.
4. All left-side rows plus matches.
5. Foreign keys.
6. A reference to another table.
7. One record linked to many.
8. Many records linked to many.
9. Reduce duplication.
10. Access related information.

## Mini Project Solution

    SELECT
        books.title,
        authors.name
    FROM books
    INNER JOIN authors
        ON books.author_id =
           authors.id;

    SELECT
        users.name,
        borrowed_books.book_id
    FROM users
    INNER JOIN borrowed_books
        ON borrowed_books.user_id =
           users.id;
