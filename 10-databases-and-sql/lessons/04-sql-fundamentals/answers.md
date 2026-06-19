# Lesson 04 Answers

1. Structured Query Language.
2. CREATE TABLE.
3. INSERT.
4. SELECT.
5. UPDATE.
6. DELETE.
7. Select all columns.
8. Create Read Update Delete.
9. INSERT.
10. It manages relational data.

## Mini Project Solution

    CREATE TABLE users (
        id SERIAL PRIMARY KEY,
        name VARCHAR(255)
    );

    INSERT INTO users (name)
    VALUES ('Ada');

    SELECT * FROM users;
