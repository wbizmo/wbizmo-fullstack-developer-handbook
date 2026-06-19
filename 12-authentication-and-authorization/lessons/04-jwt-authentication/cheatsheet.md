# Lesson 04 Cheatsheet

Install:

    npm install jsonwebtoken

Sign:

    jwt.sign(payload, secret)

Verify:

    jwt.verify(token, secret)

Header:

    Authorization: Bearer token

Status:

    401 Unauthorized

Key takeaway:
    JWTs prove identity without server-side sessions.
