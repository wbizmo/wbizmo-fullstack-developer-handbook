# Lesson 04: Caching Fundamentals

## Learning Objectives

By the end of this lesson you should be able to:

- Explain caching.
- Understand cache hits and misses.
- Reduce database load.
- Improve API performance.
- Design simple caching strategies.

## What Is Caching?

Caching stores frequently accessed data in a fast storage layer.

Instead of:

Client

↓

API

↓

Database

Every time

We use:

Client

↓

API

↓

Redis Cache

↓

Database (only if needed)

## Cache Hit

Requested data exists in cache.

Example:

    user:123

already stored.

Result:

Fast response.

## Cache Miss

Requested data does not exist in cache.

Flow:

Check Redis

↓

Not found

↓

Query database

↓

Store result in Redis

↓

Return response

## Example Flow

    const cached =
      await redis.get("user:1");

    if (cached) {
      return JSON.parse(cached);
    }

    const user =
      await db.user.findUnique({
        where: { id: 1 }
      });

    await redis.set(
      "user:1",
      JSON.stringify(user),
      {
        EX: 300
      }
    );

    return user;

## Time To Live (TTL)

TTL controls how long cache exists.

Example:

    EX 300

means:

    5 minutes

## Why Use TTL?

Prevents stale data.

Allows automatic expiration.

## Benefits

- Faster APIs
- Reduced DB load
- Lower infrastructure costs
- Better scalability

## Common Mistakes

- Caching everything.
- No expiration.
- Huge cache objects.
- Ignoring invalidation.

## Real World Examples

VaultBox:

User metadata caching.

SyncGrid:

Provider configuration caching.

inFlowForge:

Workflow definition caching.

## Exercises

1. Define caching.
2. Explain cache hit.
3. Explain cache miss.
4. Add TTL.
5. Explain why caching improves speed.

## Interview Questions

1. What is a cache hit?
2. What is a cache miss?
3. Why use Redis for caching?
4. Why use TTL?

## Summary

Caching reduces database load and improves application performance.

## References

https://redis.io/glossary/cache/
