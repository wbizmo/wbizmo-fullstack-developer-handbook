# Lesson 01: Introduction To Testing

## Learning Objectives

By the end of this lesson you should be able to:

- Explain software testing.
- Understand why testing matters.
- Identify different testing types.
- Understand testing terminology.
- Explain quality assurance basics.

## What Is Software Testing?

Software testing verifies that software behaves as expected.

Testing helps answer:

    Does this feature work?

    Does this feature still work after changes?

## Why Testing Matters

Without testing:

- Bugs increase
- Refactoring becomes risky
- Deployments become stressful
- Confidence decreases

With testing:

- Faster development
- Better quality
- Safer deployments

## Types Of Testing

### Unit Testing

Tests small pieces of code.

Example:

    calculateTotal()

### Integration Testing

Tests components working together.

Example:

API

↓

Database

### End-To-End Testing

Tests complete user workflows.

Example:

Login

↓

Dashboard

↓

Logout

## Manual Testing

Human performs tests.

Example:

Open browser.

Click buttons.

Verify results.

## Automated Testing

Code performs tests.

Example:

    expect(result)
      .toBe(100);

## Testing Pyramid

           E2E
            ▲
         Integration
            ▲
            Unit

Most tests should be unit tests.

## Common Terms

Test Case

Specific test scenario.

Assertion

Expected result.

Failure

Test did not pass.

Regression

Previously working feature breaks.

## Real World Examples

Argus:

Protocol testing.

SyncGrid:

API testing.

VaultBox:

Authentication testing.

inFlowForge:

Workflow execution testing.

## Exercises

1. Define testing.
2. Define QA.
3. Explain unit testing.
4. Explain integration testing.
5. Explain regression.

## Summary

Testing improves confidence and software quality.

Different testing levels solve different problems.

## References

https://martinfowler.com/testing/
