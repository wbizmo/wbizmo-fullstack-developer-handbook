# Lesson 05: Refresh Tokens

## Learning Objectives

By the end of this lesson you should be able to:

- Explain refresh tokens.
- Explain access token expiration.
- Understand token rotation.
- Build a refresh flow.
- Understand logout behavior.

## Why Refresh Tokens Exist

Access tokens should be short-lived.

Example:

    15 minutes

But users should not log in every 15 minutes.

Refresh tokens solve this.

## Access Token vs Refresh Token

Access Token:

- Short-lived
- Used for API access
- Sent frequently

Refresh Token:

- Longer-lived
- Used to get new access tokens
- Stored more carefully

## Refresh Flow

Login

↓

Access token issued

↓

Refresh token issued

↓

Access token expires

↓

Client sends refresh token

↓

Server issues new access token

## Example Login Response

    {
      "accessToken": "...",
      "refreshToken": "..."
    }

## Refresh Endpoint

    POST /auth/refresh

Body:

    {
      "refreshToken": "..."
    }

## Token Rotation

Token rotation means issuing a new refresh token each time refresh happens.

This improves security.

## Logout

Logout should invalidate refresh tokens.

If refresh tokens remain valid, users may still get new access tokens.

## Simple Refresh Example

    app.post("/auth/refresh", async (request, reply) => {
      const { refreshToken } = request.body;

      try {
        const payload = jwt.verify(
          refreshToken,
          process.env.REFRESH_TOKEN_SECRET
        );

        const accessToken = jwt.sign(
          {
            userId: payload.userId
          },
          process.env.JWT_SECRET,
          {
            expiresIn: "15m"
          }
        );

        return {
          accessToken
        };
      } catch {
        return reply.status(401).send({
          success: false,
          message: "Invalid refresh token"
        });
      }
    });

## Common Mistakes

- Long-lived access tokens.
- No logout invalidation.
- Storing refresh tokens insecurely.
- Reusing refresh tokens forever.
- Using the same secret for access and refresh tokens.

## Exercises

1. Explain access token.
2. Explain refresh token.
3. Create refresh endpoint.
4. Verify refresh token.
5. Issue new access token.

## Summary

Refresh tokens allow secure long-lived login sessions while keeping access tokens short-lived.

## References

https://auth0.com/docs/secure/tokens/refresh-tokens
