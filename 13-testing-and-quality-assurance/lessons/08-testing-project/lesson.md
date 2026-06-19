# Lesson 08: Testing Project

## Learning Objectives

By the end of this lesson you should be able to:

- Design a testing strategy.
- Test APIs.
- Test authentication.
- Use mocks.
- Measure coverage.
- Integrate testing into CI/CD.

## Project Overview

Build a complete test suite for:

    BookStore API

## Features

API includes:

- Registration
- Login
- Books CRUD
- Categories CRUD
- Protected routes

## Required Tests

### Authentication

Test:

- Registration
- Login
- Invalid login
- Missing token
- Invalid token

### Books

Test:

- Create book
- Read books
- Update book
- Delete book

### Validation

Test:

- Missing title
- Invalid payload
- Invalid category

### Authorization

Test:

- User access
- Admin access
- Forbidden actions

### Integration

Verify:

Route

↓

Service

↓

Database

## Mocking

Mock:

- Email service
- Payment service
- Notification service

Do not send real requests.

## Coverage Goals

Target:

    80%+

coverage

while maintaining meaningful tests.

## CI/CD

Pipeline should:

- Install dependencies
- Run tests
- Generate coverage
- Block deployment on failure

## Deliverables

- Unit tests
- Integration tests
- API tests
- Coverage report
- CI workflow

## Interview Questions

1. Difference between unit and integration tests?
2. What is mocking?
3. Why use coverage reports?
4. Why use CI/CD?
5. How do you test APIs?

## Final Challenge

Create a professional test suite that would be acceptable in a production backend project.

## Summary

Testing is not a separate activity.

Testing is part of software engineering.

## References

https://vitest.dev

https://fastify.dev/docs/latest/Guides/Testing/
