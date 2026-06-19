# Lesson 04: API Testing

## Learning Objectives

By the end of this lesson you should be able to:

- Test REST APIs.
- Verify status codes.
- Verify response bodies.
- Test validation rules.
- Test authentication-protected endpoints.

## What Is API Testing?

API testing verifies that endpoints behave correctly.

Example:

    GET /health

Expected:

    200 OK

Response:

    {
      "status": "ok"
    }

## Why API Testing Matters

APIs are contracts.

Consumers expect:

- Correct status codes
- Correct response formats
- Reliable behavior

## Fastify Testing

Example:

    const response =
      await app.inject({
        method: "GET",
        url: "/health"
      });

## Verify Status Code

    expect(
      response.statusCode
    ).toBe(200);

## Verify Response Body

    const body =
      response.json();

    expect(
      body.status
    ).toBe("ok");

## Validation Testing

Endpoint:

    POST /users

Payload:

    {}

Expected:

    400

Example:

    expect(
      response.statusCode
    ).toBe(400);

## Authentication Testing

Without token:

    GET /me

Expected:

    401

With token:

Expected:

    200

## Example Test Suite

    describe("Health Route", () => {
      it("returns 200", async () => {
        const response =
          await app.inject({
            method: "GET",
            url: "/health"
          });

        expect(
          response.statusCode
        ).toBe(200);
      });
    });

## Real World Examples

SyncGrid:

- API key validation
- Provider routes

VaultBox:

- File uploads
- Authentication

inFlowForge:

- Workflow execution

## Exercises

1. Test health endpoint.
2. Test validation failure.
3. Test authenticated route.
4. Test unauthorized route.
5. Verify JSON response.

## Summary

API testing verifies endpoint behavior and protects contracts between systems.

## References

https://fastify.dev/docs/latest/Guides/Testing/
