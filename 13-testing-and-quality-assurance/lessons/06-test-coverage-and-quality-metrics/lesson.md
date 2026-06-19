# Lesson 06: Test Coverage and Quality Metrics

## Learning Objectives

By the end of this lesson you should be able to:

- Understand test coverage.
- Measure coverage.
- Understand quality metrics.
- Interpret coverage reports.
- Avoid misleading metrics.

## What Is Coverage?

Coverage measures how much code executes during tests.

Example:

    85%

coverage.

## Types Of Coverage

### Line Coverage

Executed lines.

### Branch Coverage

Decision paths.

### Function Coverage

Executed functions.

### Statement Coverage

Executed statements.

## Generate Coverage

Vitest:

    npx vitest run --coverage

## Example Report

    Lines:
    92%

    Functions:
    95%

    Branches:
    81%

## Does 100% Coverage Mean Bug-Free?

No.

Coverage measures execution.

It does not guarantee correctness.

## Useful Quality Metrics

- Test pass rate
- Coverage
- Bug count
- Failed deployments
- Mean time to recovery

## Bad Coverage Example

    expect(true).toBe(true);

Coverage increases.

Value does not.

## Good Coverage Example

Meaningful assertions.

Real behavior tested.

## Real World Goals

Many teams target:

    70% - 90%

coverage.

Focus on quality.

Not vanity metrics.

## Exercises

1. Generate coverage report.
2. Explain branch coverage.
3. Explain function coverage.
4. Explain why 100% coverage is not enough.
5. List quality metrics.

## Summary

Coverage is useful but should never replace thoughtful testing.

## References

https://vitest.dev/guide/coverage.html
