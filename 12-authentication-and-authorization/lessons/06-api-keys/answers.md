# Lesson 06 Answers

1. Secret token for application/developer access.
2. Carries API key.
3. Usually applications/developers.
4. No.
5. Disabling a key.
6. Monitoring and auditing.
7. Limit access.
8. 401.
9. Security risk.
10. SyncGrid, inFlowForge, VaultBox.

## Exercise Solution

    async function requireApiKey(request, reply) {
      const apiKey = request.headers["x-api-key"];

      if (!apiKey) {
        return reply.status(401).send({
          success: false,
          message: "Missing API key"
        });
      }

      if (apiKey !== process.env.API_KEY) {
        return reply.status(401).send({
          success: false,
          message: "Invalid API key"
        });
      }
    }
