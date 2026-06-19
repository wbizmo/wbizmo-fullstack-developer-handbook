# Lesson 05: Mocking and Test Doubles

## Learning Objectives

By the end of this lesson you should be able to:

- Explain mocking.
- Understand test doubles.
- Isolate dependencies.
- Mock external services.
- Improve test reliability.

## Why Mock?

Real dependencies can be:

- Slow
- Expensive
- Unreliable

Examples:

- Stripe
- Redis
- Email services
- External APIs

## Test Doubles

Common types:

- Dummy
- Stub
- Mock
- Fake
- Spy

Most developers commonly use mocks and spies.

## Example Problem

Function:

    sendWelcomeEmail()

Depends on:

    External email provider

We don't want tests sending real emails.

## Mock Example

    vi.mock(
      "../services/email.js"
    );

## Spy Example

    const spy =
      vi.spyOn(
        emailService,
        "send"
      );

## Mock Return Value

    vi.spyOn(
      userService,
      "getUser"
    ).mockResolvedValue({
      id: 1,
      name: "Ada"
    });

## Why Mock?

Benefits:

- Faster tests
- Deterministic results
- No external dependencies

## What Not To Mock

Avoid mocking everything.

If everything is mocked:

You may not test real behavior.

## Real World Examples

SyncGrid:

Mock payment providers.

VaultBox:

Mock storage provider.

inFlowForge:

Mock webhook delivery.

Argus:

Mock distributed node responses.

## Exercises

1. Define mock.
2. Define spy.
3. Mock a service.
4. Mock return values.
5. Explain when mocking is useful.

## Summary

Mocks isolate dependencies and improve testing speed and reliability.

## References

https://vitest.dev/guide/mocking.html
