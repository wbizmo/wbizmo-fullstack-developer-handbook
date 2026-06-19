# Lesson 02 Answers

1. Security.
2. One-way transformation.
3. No.
4. bcrypt.
5. Creates hash.
6. Verifies password.
7. Secure password storage.
8. Hash.
9. Plain password.
10. Protect users.

## Exercise Solution

    const hash =
      await bcrypt.hash(
        password,
        10
      );

    const valid =
      await bcrypt.compare(
        password,
        hash
      );
