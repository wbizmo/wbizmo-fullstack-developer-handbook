# Lesson 10: Authentication System Project

## Learning Objectives

By the end of this lesson you should be able to:

- Design an authentication system.
- Implement registration.
- Implement login.
- Issue JWTs.
- Use refresh tokens.
- Protect routes.
- Add roles.
- Secure sensitive operations.

## Project Overview

Build:

    Auth Service

Features:

- Register
- Login
- Refresh Token
- Logout
- Protected Profile Route
- Admin Route
- API Key Protected Route

## Suggested Models

User:

    id
    email
    passwordHash
    role
    createdAt

RefreshToken:

    id
    userId
    tokenHash
    expiresAt
    revokedAt

ApiKey:

    id
    ownerId
    prefix
    keyHash
    scopes
    revokedAt
    lastUsedAt

## Register Flow

Receive:

    email
    password

Hash password.

Create user.

Return safe user data.

## Login Flow

Find user.

Compare password.

Issue access token.

Issue refresh token.

## Protected Route

    GET /me

Requires:

    Authorization: Bearer token

## Admin Route

    GET /admin/users

Requires:

- authenticated user
- admin role

## API Key Route

    GET /developer/usage

Requires:

    x-api-key

## Security Requirements

- No plain passwords.
- No full token logging.
- JWT secret from environment.
- Refresh token revocation.
- RBAC.
- Validation.
- Rate limiting planned.

## Final Challenge

Create a Fastify Auth API with:

    POST /auth/register
    POST /auth/login
    POST /auth/refresh
    POST /auth/logout
    GET /me
    GET /admin/users
    GET /developer/usage

## Summary

A real authentication system combines:

- identity
- password security
- token management
- authorization
- API security
- production safeguards

## References

https://owasp.org/www-project-api-security/

https://jwt.io
