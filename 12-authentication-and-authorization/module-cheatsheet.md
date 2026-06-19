# Authentication & Authorization Module Cheatsheet

Authentication:
    Who are you?

Authorization:
    What can you do?

Password Hash:

    bcrypt.hash()

Password Verify:

    bcrypt.compare()

JWT:

    jwt.sign()
    jwt.verify()

Header:

    Authorization: Bearer token

API Key:

    x-api-key

401:
    Unauthorized

403:
    Forbidden

RBAC:
    Role Based Access Control

OAuth:
    Delegated authorization

Security:
    HTTPS
    Rate limiting
    secure cookies
    env secrets
    no secret logging
