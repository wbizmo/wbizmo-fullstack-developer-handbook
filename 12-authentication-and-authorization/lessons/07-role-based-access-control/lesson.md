# Lesson 07: Role Based Access Control

## Learning Objectives

By the end of this lesson you should be able to:

- Explain Role Based Access Control.
- Understand roles.
- Understand permissions.
- Protect routes by role.
- Design simple authorization systems.

## What Is RBAC?

RBAC means:

    Role Based Access Control

It controls what users can do based on their role.

## Common Roles

Examples:

- user
- admin
- owner
- manager
- editor
- viewer

## Authentication vs Authorization

Authentication:

    Who are you?

Authorization:

    What are you allowed to do?

RBAC belongs to authorization.

## Example

Admin:

- create users
- delete users
- view all records

User:

- view own profile
- update own profile

Viewer:

- read only

## User Object

Example:

    const user = {
      id: "user_1",
      email: "ada@example.com",
      role: "admin"
    };

## Protect By Role

Example:

    function requireRole(role) {
      return async function (request, reply) {
        if (request.user.role !== role) {
          return reply.status(403).send({
            success: false,
            message: "Forbidden"
          });
        }
      };
    }

## Protected Admin Route

    app.get(
      "/admin/users",
      {
        preHandler: [
          requireAuth,
          requireRole("admin")
        ]
      },
      async () => {
        return {
          users: []
        };
      }
    );

## 401 vs 403

401 means:

    Not authenticated

403 means:

    Authenticated but not allowed

## Permission Based Access

Sometimes roles are not enough.

Example:

Admin has permissions:

- users.read
- users.delete
- billing.manage

Permission checks are more flexible.

## Common Mistakes

- Treating every user as admin.
- Confusing 401 and 403.
- Trusting role from frontend only.
- Not checking permissions on backend.
- Hardcoding messy role checks everywhere.

## Exercises

1. Create user role.
2. Create admin role.
3. Create requireRole helper.
4. Protect admin route.
5. Return 403 for wrong role.
6. Explain 401 vs 403.

## Summary

RBAC controls access based on roles.

Authorization checks must happen on the backend.

Roles and permissions keep systems safe.

## References

https://owasp.org/www-project-api-security/
