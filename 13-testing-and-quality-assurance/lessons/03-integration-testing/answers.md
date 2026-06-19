# Lesson 03 Answers

1. Testing components together.
2. Larger scope.
3. Component interaction.
4. Verify API behavior.
5. Security.
6. Fastify testing helper.
7. No.
8. Prevent contamination.
9. Catch interaction bugs.
10. Integration layer.

## Exercise Solution

    const response =
      await app.inject({
        method: "GET",
        url: "/health"
      });

    expect(
      response.statusCode
    ).toBe(200);
