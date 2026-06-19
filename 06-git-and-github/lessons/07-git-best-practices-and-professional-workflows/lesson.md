# Lesson 07: Git Best Practices And Professional Workflows

## Learning Objectives

- Write better commits
- Use branches effectively
- Understand professional workflows
- Avoid common mistakes

## Best Practice 1

Commit often.

Bad:

    1 commit after 3 months

Good:

    Many meaningful commits

## Best Practice 2

Write meaningful commit messages.

Good:

    Add JWT authentication

Bad:

    update

## Best Practice 3

Use branches.

Avoid:

    Direct production edits

## Best Practice 4

Pull before pushing.

    git pull
    git push

## Best Practice 5

Never commit secrets.

Examples:

- API keys
- Passwords
- Tokens

Use:

    .env

## Best Practice 6

Use .gitignore

Example:

    node_modules
    .env
    dist

## Best Practice 7

Document repositories.

Include:

- README
- Installation
- Usage
- Screenshots

## Professional Workflow

Issue

↓

Branch

↓

Code

↓

Commit

↓

Push

↓

PR

↓

Review

↓

Merge

## Summary

Professional developers use Git daily.

Good habits create maintainable projects.
