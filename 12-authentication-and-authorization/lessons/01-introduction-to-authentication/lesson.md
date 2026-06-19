# Lesson 01: Introduction To Authentication

## Learning Objectives

By the end of this lesson you should be able to:

- Define authentication.
- Define authorization.
- Explain the difference between them.
- Understand identity verification.
- Understand protected systems.

## What Is Authentication?

Authentication answers:

    Who are you?

Examples:

- Username and password
- Email and password
- Fingerprint
- Face ID
- API Key
- JWT

Authentication verifies identity.

## Real World Examples

Bank App:

You log in.

System verifies identity.

Authentication.

Netflix:

You sign in.

Authentication.

GitHub:

You enter credentials.

Authentication.

## What Is Authorization?

Authorization answers:

    What are you allowed to do?

Example:

Admin:

Can delete users.

Regular user:

Cannot delete users.

Identity is already verified.

Now permissions are checked.

## Authentication vs Authorization

Authentication:

    Who are you?

Authorization:

    What can you do?

Authentication happens first.

Authorization happens second.

## Example Flow

User:

    Login

↓

Authentication

↓

Receive Access

↓

Authorization Checks

↓

Protected Resources

## Protected Resources

Examples:

- User profile
- Payments
- Admin dashboard
- API routes
- File storage

## Portfolio Examples

Used in:

- VaultBox
- SyncGrid
- inFlowForge
- Cashflowr
- Covenant

## Exercises

1. Define authentication.
2. Define authorization.
3. Explain differences.
4. List protected resources.
5. Draw auth flow.

## Summary

Authentication verifies identity.

Authorization controls permissions.

Both are critical for secure systems.

## References

https://owasp.org/www-project-top-ten/
