# Lesson 05: Cache Patterns

## Learning Objectives

By the end of this lesson you should be able to:

- Understand cache strategies.
- Use cache-aside.
- Use write-through.
- Understand invalidation.
- Choose appropriate patterns.

## Why Cache Patterns Matter

Caching without strategy creates:

- Stale data
- Inconsistent responses
- Difficult debugging

## Cache-Aside Pattern

Most common pattern.

Flow:

Request

↓

Check Cache

↓

Miss

↓

Query Database

↓

Store Cache

↓

Return Result

Example:

    const cached =
      await redis.get(key);

    if (cached) {
      return JSON.parse(cached);
    }

    const data =
      await db.query();

    await redis.set(
      key,
      JSON.stringify(data)
    );

    return data;

## Write-Through Pattern

Update:

Database

↓

Cache

Both updated immediately.

Benefits:

- Consistent cache

Tradeoff:

- More writes

## Write-Behind Pattern

Write:

Cache

↓

Database later

Benefits:

- Faster writes

Risk:

- Data loss if not handled carefully

## Cache Invalidation

One of the hardest problems in software.

Example:

User updates profile.

Old cache must be removed.

    await redis.del(
      "user:1"
    );

## Common Invalidation Methods

- TTL expiration
- Explicit deletion
- Event-driven invalidation

## Real World Usage

Cache-Aside:

Most APIs.

Write-Through:

Financial systems.

Write-Behind:

Analytics systems.

## Common Mistakes

- Never invalidating cache.
- Infinite TTL.
- Storing massive objects.
- Wrong cache keys.

## Exercises

1. Explain cache-aside.
2. Explain write-through.
3. Explain write-behind.
4. Invalidate cache.
5. Compare patterns.

## Interview Questions

1. What is cache-aside?
2. What is cache invalidation?
3. Why is cache invalidation difficult?
4. What cache strategy is most common?

## Summary

Caching patterns determine how applications maintain speed and consistency.

## References

https://learn.microsoft.com/azure/architecture/patterns/cache-aside
