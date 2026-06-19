# Lesson 04: JWT Authentication

## Learning Objectives

By the end of this lesson you should be able to:

- Explain JWT authentication.
- Understand access tokens.
- Sign tokens.
- Verify tokens.
- Protect API routes.

## What Is JWT?

JWT means:

    JSON Web Token

A JWT is a signed token used to prove identity.

It usually contains:

- user id
- email
- role
- expiration time

## JWT Flow

User logs in.

↓

Server verifies credentials.

↓

Server signs token.

↓

Client stores token.

↓

Client sends token with requests.

↓

Server verifies token.

## Authorization Header

Clients usually send JWTs like this:

    Authorization: Bearer token_here

## Install jsonwebtoken

    npm install jsonwebtoken

## Sign Token

    import jwt from "jsonwebtoken";

    const token = jwt.sign(
      {
        userId: user.id,
        role: user.role
      },
      process.env.JWT_SECRET,
      {
        expiresIn: "15m"
      }
    );

## Verify Token

    const payload = jwt.verify(
      token,
      process.env.JWT_SECRET
    );

## Protected Route Middleware

    function requireAuth(request, reply, done) {
      const header = request.headers.authorization;

      if (!header) {
        return reply.status(401).send({
          success: false,
          message: "Missing token"
        });
      }

      const token = header.replace("Bearer ", "");

      try {
        const payload = jwt.verify(
          token,
          process.env.JWT_SECRET
        );

        request.user = payload;

        done();
      } catch {
        return reply.status(401).send({
          success: false,
          message: "Invalid token"
        });
      }
    }

## Fastify Protected Route

    app.get(
      "/me",
      {
        preHandler: requireAuth
      },
      async (request) => {
        return {
          user: request.user
        };
      }
    );

## Common Mistakes

- Using weak secrets.
- Storing secrets in code.
- Making tokens last forever.
- Not verifying tokens.
- Putting sensitive data inside JWT payload.

## Exercises

1. Install jsonwebtoken.
2. Create a JWT.
3. Verify a JWT.
4. Create requireAuth middleware.
5. Protect GET /me.

## Summary

JWTs are signed tokens used for stateless authentication.

They are common in APIs and frontend-backend applications.

## References

https://jwt.io

https://www.npmjs.com/package/jsonwebtoken
