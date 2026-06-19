# Lesson 04: Branches, Merging and Conflict Resolution

## Learning Objectives

By the end of this lesson, you should understand:

- What branches are
- Why branches exist
- How to create branches
- How to switch branches
- How to merge branches
- What merge conflicts are
- How to resolve conflicts

## What Is A Branch?

A branch is an independent line of development.

Think of it as:

    Alternative Timeline

Main branch:

    main

Feature branch:

    feature-auth

Bug fix branch:

    fix-login

## Why Use Branches?

Branches allow developers to:

- Work safely
- Experiment
- Build features
- Fix bugs
- Avoid breaking production code

## View Branches

    git branch

## Create Branch

    git branch feature-auth

## Switch Branch

    git checkout feature-auth

Modern Git:

    git switch feature-auth

## Create And Switch

    git checkout -b feature-auth

or

    git switch -c feature-auth

## Merge Branch

Move to main:

    git switch main

Merge:

    git merge feature-auth

## Merge Conflicts

A conflict happens when Git cannot determine which change should win.

Example:

Developer A edits line 10.

Developer B edits line 10.

Git needs help deciding.

## Resolving Conflicts

Git marks conflict areas.

You manually choose:

- Your change
- Their change
- Combination

Then:

    git add .
    git commit

## Exercises

1. Create a branch.
2. Switch branches.
3. Create a commit on a branch.
4. Merge the branch.
5. Simulate a merge conflict.

## Summary

Branches allow isolated development.

Merging combines work.

Conflicts are normal and solvable.

## References

https://git-scm.com/book/en/v2/Git-Branching
