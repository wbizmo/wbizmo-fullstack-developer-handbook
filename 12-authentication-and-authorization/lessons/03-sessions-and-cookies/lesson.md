# Lesson 03: Sessions and Cookies

## Learning Objectives

By the end of this lesson you should be able to:

- Understand sessions.
- Understand cookies.
- Explain session authentication.
- Understand stateful authentication.
- Compare sessions and JWTs.

## What Is A Session?

A session stores user state on the server.

Example:

User logs in.

Server creates session.

Session stored.

User receives session identifier.

## What Is A Cookie?

Cookie:

Small piece of data stored in browser.

Example:

    session_id=abc123

Browser sends cookie automatically.

## Session Flow

Login

↓

Server verifies password

↓

Session created

↓

Cookie returned

↓

Cookie sent on future requests

## Example

Cookie:

    session_id=12345

Server:

Find session.

Find user.

Grant access.

## Advantages

- Easy logout
- Centralized control
- Session invalidation

## Disadvantages

- Requires server-side storage
- Scaling complexity

## Sessions vs JWT

Sessions:

Server stores state.

JWT:

Client stores token.

## Modern Usage

Many traditional applications:

- Laravel
- WordPress
- Admin panels

use sessions.

Many APIs use JWT.

## Exercises

1. Define session.
2. Define cookie.
3. Explain session flow.
4. Compare sessions and JWTs.
5. Explain stateful authentication.

## Summary

Sessions store authentication state.

Cookies carry session identifiers.

Sessions remain common in web applications.

## References

https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies
