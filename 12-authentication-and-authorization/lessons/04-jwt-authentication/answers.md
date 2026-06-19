# Lesson 04 Answers

1. JSON Web Token.
2. A token used to access protected resources.
3. Creates a signed token.
4. Validates a signed token.
5. Environment variables.
6. Authorization.
7. Token authentication scheme.
8. Reduce risk if stolen.
9. No.
10. 401.

## Exercise Solution

    const token = jwt.sign(
      {
        userId: "user_1",
        role: "user"
      },
      process.env.JWT_SECRET,
      {
        expiresIn: "15m"
      }
    );

    const payload = jwt.verify(
      token,
      process.env.JWT_SECRET
    );
