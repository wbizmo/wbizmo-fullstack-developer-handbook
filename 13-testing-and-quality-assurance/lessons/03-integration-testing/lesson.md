# Lesson 03: Integration Testing

## Learning Objectives

By the end of this lesson you should be able to:

- Explain integration testing.
- Test multiple components together.
- Understand API and database testing.
- Understand integration test value.
- Compare unit and integration tests.

## What Is Integration Testing?

Integration testing verifies that components work together.

Example:

Route

↓

Service

↓

Database

All tested together.

## Example

User registration:

Route

↓

Validation

↓

Database

↓

Response

Integration test verifies entire flow.

## Unit vs Integration

Unit:

One function.

Integration:

Multiple components.

## API Example

Endpoint:

    POST /users

Tests:

- validation
- service
- database
- response

## Fastify Example

    const response =
      await app.inject({
        method: "GET",
        url: "/health"
      });

    expect(
      response.statusCode
    ).toBe(200);

## What Should Integration Tests Verify?

- Route behavior
- Validation
- Database access
- Authentication
- Authorization

## Common Mistakes

- Too much mocking.
- Testing implementation details.
- Depending on production databases.
- Ignoring cleanup.

## Exercises

1. Test route.
2. Test service.
3. Test validation.
4. Test authentication.
5. Explain integration testing.

## Summary

Integration tests verify components working together.

They catch issues unit tests cannot detect.

## References

https://fastify.dev/docs/latest/Guides/Testing/
