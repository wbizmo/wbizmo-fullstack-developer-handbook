# Lesson 07 Answers

1. Role Based Access Control.
2. Authorization.
3. user, admin, owner.
4. Not authenticated.
5. Forbidden.
6. Yes.
7. Frontend can be manipulated.
8. Specific allowed actions.
9. Reusable authorization.
10. Protect resources.

## Exercise Solution

    function requireRole(role) {
      return async function (request, reply) {
        if (!request.user) {
          return reply.status(401).send({
            success: false,
            message: "Unauthorized"
          });
        }

        if (request.user.role !== role) {
          return reply.status(403).send({
            success: false,
            message: "Forbidden"
          });
        }
      };
    }
