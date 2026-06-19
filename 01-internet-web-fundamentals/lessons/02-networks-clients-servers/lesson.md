# Lesson 02: Networks, Clients and Servers

## Learning Objectives

By the end of this lesson, you should understand networks, clients, servers, requests, responses, and how web applications use client-server communication.

## What Is A Network?

A network is a group of connected devices that can communicate.

Examples:

- Home Wi-Fi
- School network
- Office network
- Mobile network
- Data center network

The internet is a massive connection of many smaller networks.

## What Is A Client?

A client is a device or program that requests something.

Examples:

- Browser
- Mobile app
- Desktop app
- API testing tool
- React frontend

## What Is A Server?

A server is a computer or program that provides something.

Examples:

- Website server
- API server
- Database server
- File server
- Email server

## Client-Server Model

Most web applications follow this pattern:

    Client → Request → Server
    Client ← Response ← Server

Example:

    Browser asks for webpage.
    Server sends webpage.

## Real Example

When you log into an app:

    1. You enter email and password.
    2. The frontend sends login data to the backend.
    3. The backend checks the database.
    4. The backend sends success or failure response.
    5. The frontend updates the screen.

## Frontend and Backend

Frontend usually acts as the client.

Backend usually acts as the server.

But servers can also talk to other servers.

Example:

    Your API → Payment API
    Your API → Email API
    Your API → Storage API

## Request and Response

A request is a message asking for something.

A response is the answer.

Example:

    Request: Give me the homepage.
    Response: Here is the HTML.

## Why This Matters

Full stack development is mostly about building systems where clients and servers communicate correctly.

## Common Mistakes

- Thinking frontend and backend are the same thing
- Thinking the browser stores all websites
- Forgetting that APIs are servers too
- Ignoring request and response errors

## Exercises

1. Identify the client and server when you visit YouTube.
2. Identify the client and server when a mobile app loads messages.
3. Explain the request-response cycle.
4. List three examples of servers.
5. Explain why frontend apps need backend APIs.

## Summary

Clients request resources. Servers provide resources. Most web applications depend on this relationship.
