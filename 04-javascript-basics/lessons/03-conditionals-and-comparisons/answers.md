# Lesson 03 Answers: Conditionals and Comparisons

1. An if statement runs code only when a condition is true.
2. else runs when the if condition is false.
3. else if checks another condition.
4. == compares with type conversion. === compares value and type strictly.
5. Greater than.
6. Greater than or equal to.
7. AND.
8. OR.
9. NOT, it reverses a boolean.
10. false, 0, "", null, undefined, NaN.

## Exercise Solution

    const age = 20;

    if (age >= 18) {
      console.log("Adult");
    } else {
      console.log("Minor");
    }

    const isLoggedIn = true;

    if (isLoggedIn) {
      console.log("Welcome back");
    }

    const score = 82;

    if (score >= 90) {
      console.log("Excellent");
    } else if (score >= 70) {
      console.log("Good");
    } else {
      console.log("Keep practicing");
    }

    const password = "secret123";

    if (password.length >= 8) {
      console.log("Password length is valid");
    }

    const isVerified = true;

    if (isLoggedIn && isVerified) {
      console.log("User can access dashboard");
    }

    const isAdmin = false;
    const isOwner = true;

    if (isAdmin || isOwner) {
      console.log("User has access");
    }

    const isBlocked = false;

    if (!isBlocked) {
      console.log("User is allowed");
    }
