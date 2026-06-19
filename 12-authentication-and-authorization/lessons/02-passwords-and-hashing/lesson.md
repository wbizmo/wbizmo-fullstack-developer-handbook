# Lesson 02: Passwords and Hashing

## Learning Objectives

By the end of this lesson you should be able to:

- Understand password storage.
- Understand hashing.
- Use bcrypt.
- Verify passwords.
- Understand password security.

## Never Store Plain Passwords

Bad:

    password123

Stored directly.

If database leaks:

Everyone's password exposed.

## What Is Hashing?

Hashing converts:

    password

into

    unreadable value

Example:

    password123

becomes:

    $2b$10$...

Hashing is one-way.

## bcrypt

Popular password hashing library.

Install:

    npm install bcrypt

## Hash Password

Example:

    import bcrypt
      from "bcrypt";

    const hash =
      await bcrypt.hash(
        password,
        10
      );

## Store Hash

Store:

    hash

Never:

    password

## Verify Password

Example:

    const valid =
      await bcrypt.compare(
        password,
        hash
      );

Returns:

    true

or

    false

## Registration Flow

User registers.

↓

Password hashed.

↓

Hash stored.

## Login Flow

User enters password.

↓

Compare password.

↓

Authentication result.

## Common Mistakes

Bad:

- Plain text passwords
- Weak passwords
- Custom hashing algorithms

Good:

- bcrypt
- Strong passwords
- Rate limiting

## Exercises

1. Install bcrypt.
2. Hash password.
3. Verify password.
4. Explain why hashing exists.
5. Explain why plain passwords are dangerous.

## Summary

Passwords should never be stored directly.

Hashing protects users.

bcrypt is a common solution.

## References

https://www.npmjs.com/package/bcrypt
