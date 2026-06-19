# Lesson 02 Answers

1. Testing small units.
2. Small scope.
3. Testing framework.
4. Creates assertion.
5. Checks equality.
6. Setup.
7. Execute code.
8. Verify result.
9. No.
10. Reliability.

## Exercise Solution

    export function add(a, b) {
      return a + b;
    }

    expect(
      add(2, 3)
    ).toBe(5);
