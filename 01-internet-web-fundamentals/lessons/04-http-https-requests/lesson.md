# Lesson 04: HTTP, HTTPS and Requests

## Learning Objectives

By the end of this lesson, you should understand HTTP, HTTPS, requests, responses, methods, status codes, headers, and why secure communication matters.

## What Is HTTP?

HTTP means HyperText Transfer Protocol.

It is the main protocol browsers use to communicate with web servers.

Simple flow:

    Browser sends HTTP request.
    Server sends HTTP response.

## What Is HTTPS?

HTTPS is the secure version of HTTP.

The S means Secure.

HTTPS encrypts communication between the client and server.

This protects sensitive information such as:

- Passwords
- Tokens
- Payment details
- Personal data

## Request

A request is sent by the client.

A request may include:

- Method
- URL
- Headers
- Body

## Response

A response is sent by the server.

A response may include:

- Status code
- Headers
- Body

## HTTP Methods

GET:
    Retrieve data.

POST:
    Create or submit data.

PUT:
    Replace data.

PATCH:
    Update part of data.

DELETE:
    Delete data.

## Examples

GET request:

    GET /products

POST request:

    POST /login

DELETE request:

    DELETE /users/12

## Status Codes

Status codes describe the result of a request.

Common examples:

200:
    OK

201:
    Created

400:
    Bad Request

401:
    Unauthorized

403:
    Forbidden

404:
    Not Found

500:
    Server Error

## Headers

Headers contain metadata about the request or response.

Examples:

    Content-Type: application/json
    Authorization: Bearer token
    Accept: application/json

## Body

The body contains data sent with the request or response.

Example JSON body:

    {
      "email": "user@example.com",
      "password": "secret"
    }

## Why HTTPS Matters

Without HTTPS, attackers may intercept sensitive data.

Modern browsers warn users when websites are not secure.

Production websites should use HTTPS.

## APIs and HTTP

Most backend APIs communicate using HTTP.

Example:

    Frontend → HTTP Request → Backend API
    Frontend ← HTTP Response ← Backend API

## Common Mistakes

- Using GET for sensitive form submission
- Ignoring status codes
- Not sending correct headers
- Forgetting HTTPS in production
- Confusing 401 and 403

## Exercises

1. Explain HTTP.
2. Explain HTTPS.
3. Name five HTTP methods.
4. Explain status code 404.
5. Explain status code 500.
6. Write a sample login request body.
7. Explain why HTTPS is important.

## Summary

HTTP powers web communication. HTTPS secures it. Requests and responses are the foundation of websites and APIs.
