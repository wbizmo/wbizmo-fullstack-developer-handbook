# Lesson 02: Unit Testing

## Learning Objectives

By the end of this lesson you should be able to:

- Explain unit testing.
- Write unit tests.
- Use assertions.
- Test functions.
- Understand test isolation.

## What Is Unit Testing?

Unit testing verifies small pieces of code independently.

Example:

    calculateTax()

Only test that function.

## Why Unit Tests Matter

Benefits:

- Fast
- Reliable
- Easy to run
- Easy to debug

## Testing Frameworks

JavaScript:

- Vitest
- Jest

Node.js:

- Vitest
- Jest
- Node Test Runner

## Install Vitest

    npm install -D vitest

## Function Example

    export function add(a, b) {
      return a + b;
    }

## Unit Test

    import { describe, it, expect }
      from "vitest";

    import { add }
      from "./math.js";

    describe("add", () => {
      it("adds numbers", () => {
        expect(
          add(2, 3)
        ).toBe(5);
      });
    });

## Run Tests

    npx vitest

## Test Structure

Arrange

↓

Act

↓

Assert

## Multiple Tests

    it("adds positives", () => {});

    it("adds negatives", () => {});

    it("adds zero", () => {});

## Good Unit Tests

- Small
- Focused
- Fast
- Independent

## Bad Unit Tests

- Depend on database
- Depend on network
- Depend on external APIs

## Exercises

1. Install Vitest.
2. Create add function.
3. Test add function.
4. Create subtract function.
5. Test subtract function.

## Summary

Unit tests verify individual units of logic.

They form the foundation of automated testing.

## References

https://vitest.dev
