# Lesson 09: Authentication Security Best Practices

## Learning Objectives

By the end of this lesson you should be able to:

- Identify common auth risks.
- Secure passwords.
- Secure tokens.
- Protect APIs.
- Understand production auth practices.

## Security Is Not Optional

Authentication mistakes can expose:

- User accounts
- Payments
- Files
- Admin dashboards
- Private data

## Password Best Practices

- Hash passwords.
- Use bcrypt or Argon2.
- Never store plain passwords.
- Enforce reasonable password rules.
- Rate limit login attempts.

## Token Best Practices

- Use strong secrets.
- Use short access token expiry.
- Use refresh tokens carefully.
- Do not store sensitive data in JWT payload.
- Rotate refresh tokens when possible.

## API Key Best Practices

- Store hashed keys.
- Show full key only once.
- Use prefixes.
- Allow revocation.
- Track last used time.
- Scope permissions.

## Cookie Security

Use:

    httpOnly

Use:

    secure

Use:

    sameSite

These reduce common browser-based attacks.

## Rate Limiting

Rate limiting prevents abuse.

Examples:

- Login brute force
- API spam
- Password guessing

## Logging

Log:

- failed logins
- key usage
- suspicious activity

Do not log:

- passwords
- full tokens
- full API keys

## Common Attacks

- Brute force
- Credential stuffing
- Token theft
- Session hijacking
- CSRF
- XSS

## Production Checklist

- Hash passwords.
- Use HTTPS.
- Use secure cookies.
- Use rate limiting.
- Validate input.
- Use environment variables.
- Rotate secrets.
- Revoke compromised tokens.
- Audit sensitive actions.

## Exercises

1. Create auth security checklist.
2. Explain why HTTPS matters.
3. Explain why tokens expire.
4. Explain why passwords are hashed.
5. Explain why logs should not contain secrets.

## Summary

Authentication security requires multiple layers.

Good systems assume credentials can be attacked and design defenses.

## References

https://owasp.org/www-project-top-ten/

https://owasp.org/www-project-api-security/
