# Lesson 08: OAuth and Social Login

## Learning Objectives

By the end of this lesson you should be able to:

- Explain OAuth.
- Understand social login.
- Understand authorization codes.
- Understand third-party identity providers.
- Know when to use OAuth.

## What Is OAuth?

OAuth is an authorization framework that allows applications to access resources without directly handling user passwords.

Common providers:

- Google
- GitHub
- Facebook
- Microsoft
- Apple

## Social Login

Social login allows users to sign in with another provider.

Example:

    Continue with Google

or:

    Continue with GitHub

## Why OAuth Exists

Without OAuth:

Users would give your app their Google password.

That is unsafe.

With OAuth:

Google authenticates the user.

Your app receives limited access.

## OAuth Flow Simplified

User clicks:

    Continue with Google

↓

Redirect to Google

↓

User approves

↓

Google redirects back with code

↓

Backend exchanges code for tokens

↓

Application creates or finds user

## Authorization Code

The authorization code is temporary.

It is exchanged for tokens.

## Access Token

Used to access provider resources.

Example:

    Get user profile

## Common Use Cases

- Login with Google
- Login with GitHub
- Connect Stripe account
- Connect Slack workspace
- Connect Google Calendar

## OAuth vs Password Login

Password login:

Your system stores password hash.

OAuth:

External provider verifies identity.

## Common Mistakes

- Exposing client secrets.
- Handling OAuth only on frontend.
- Not validating provider responses.
- Requesting too many permissions.
- Not handling failed redirects.

## Exercises

1. Explain OAuth.
2. Explain social login.
3. Draw OAuth flow.
4. List providers.
5. Compare OAuth and password login.

## Summary

OAuth allows secure delegated access.

Social login improves user experience.

OAuth is important for modern integrations and authentication systems.

## References

https://oauth.net/2/

https://auth0.com/intro-to-iam/what-is-oauth-2
