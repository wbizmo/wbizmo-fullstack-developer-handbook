# Lesson 06: API Keys

## Learning Objectives

By the end of this lesson you should be able to:

- Explain API keys.
- Understand developer authentication.
- Create API key middleware.
- Store hashed API keys.
- Protect integration APIs.

## What Is An API Key?

An API key is a secret token used to identify an application or developer.

Example:

    x-api-key: sk_live_abc123

API keys are common in:

- Payment APIs
- Email APIs
- Storage APIs
- Integration platforms
- Developer tools

## API Keys vs User Login

User login:

    Human identity

API key:

    Application or developer identity

## Portfolio Examples

API keys are important in:

- SyncGrid API
- inFlowForge API
- VaultBox API

## Header

Common API key header:

    x-api-key

## Simple Middleware

    async function requireApiKey(request, reply) {
      const apiKey = request.headers["x-api-key"];

      if (!apiKey) {
        return reply.status(401).send({
          success: false,
          message: "Missing API key"
        });
      }

      if (apiKey !== process.env.API_KEY) {
        return reply.status(401).send({
          success: false,
          message: "Invalid API key"
        });
      }
    }

## Protect Route

    app.get(
      "/protected",
      {
        preHandler: requireApiKey
      },
      async () => {
        return {
          success: true
        };
      }
    );

## Hashing API Keys

Production systems should not store raw API keys.

Store:

    hash(apiKey)

Verify incoming key by comparing hashes.

## API Key Metadata

A good system tracks:

- key id
- owner
- prefix
- hash
- permissions
- created_at
- revoked_at
- last_used_at

## Revocation

API keys should be revocable.

Example:

    revoked_at IS NOT NULL

means the key is no longer valid.

## Common Mistakes

- Storing raw API keys.
- No revocation.
- No rate limits.
- No scopes.
- Logging full API keys.
- Using one global key forever.

## Exercises

1. Create API key middleware.
2. Read x-api-key.
3. Reject missing key.
4. Reject invalid key.
5. Protect route.
6. Explain why raw keys should not be stored.

## Summary

API keys authenticate applications and developers.

They are critical for platform APIs and integration systems.

## References

https://owasp.org/www-project-api-security/
