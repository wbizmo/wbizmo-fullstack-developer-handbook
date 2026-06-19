# Lesson 09 Answers

1. users, authors, categories, books, borrowed_books.
2. Reduce duplication.
3. Reduce duplication.
4. Track borrowing events.
5. Connection between records.
6. Performance.
7. Controlled schema evolution.
8. borrowed_books.
9. users.
10. Scalability and maintainability.

## Project Solution

Tables:

    users
    authors
    categories
    books
    borrowed_books

Indexes:

    users.email
    books.title
    borrowed_books.user_id
    borrowed_books.book_id
