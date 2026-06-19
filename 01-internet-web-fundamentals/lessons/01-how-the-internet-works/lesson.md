# Lesson 01: How The Internet Works

## Learning Objectives

By the end of this lesson, you should be able to:

- Explain what the internet is.
- Understand the difference between the internet and the web.
- Explain how devices communicate across networks.
- Understand what ISPs, routers, packets, and IP addresses do.
- Explain why data is broken into packets.
- Describe the basic journey of data from your device to a server and back.
- Understand why the internet is called a network of networks.

## Introduction

The internet is one of the most important technologies in the modern world.

Every time you open a website, send a message, stream a video, use a banking app, make an API request, or deploy a web application, you are using the internet.

As a full stack developer, you do not need to become a network engineer before writing code.

However, you should understand the basics of how the internet works because web development depends on it.

When you build a frontend application, that application usually talks to a backend server.

When you build an API, users and applications access it through the internet.

When you deploy a website, people reach it through browsers, DNS, hosting providers, servers, and HTTP.

Understanding the internet helps you understand the foundation beneath websites, APIs, cloud hosting, and full stack applications.

## What Is The Internet?

The internet is a global system of connected computer networks.

A simple definition:

    The internet is a worldwide network of networks that allows devices to communicate.

It connects:

- Phones
- Laptops
- Servers
- Routers
- Data centers
- Smart TVs
- Game consoles
- Cloud platforms
- Websites
- APIs

The internet is not one single computer.

It is not one company.

It is not the same thing as Google, Facebook, or YouTube.

It is the infrastructure that allows devices and services to communicate globally.

## Internet vs Web

Many beginners use "internet" and "web" as if they mean the same thing.

They are related, but they are not the same.

## The Internet

The internet is the global network infrastructure.

It allows devices to exchange data.

Examples of things that use the internet:

- Websites
- Email
- WhatsApp
- Online games
- Video calls
- APIs
- Cloud storage
- Streaming services

## The Web

The web, also called the World Wide Web, is one service that runs on the internet.

The web uses:

- Browsers
- Websites
- URLs
- HTML
- CSS
- JavaScript
- HTTP and HTTPS

When you open a website in Chrome, you are using the web.

When you send an email, you are using the internet, but not necessarily the web.

Simple comparison:

| Concept | Meaning |
|---|---|
| Internet | Global network infrastructure |
| Web | Websites and webpages accessed through browsers |
| Browser | Software used to access the web |
| Website | A collection of web pages and resources |

## What Is A Network?

A network is a group of connected devices that can communicate with each other.

Example:

At home, your phone, laptop, and smart TV may all connect to the same Wi-Fi router.

That creates a small local network.

Your home network may look like this:

    Phone
       \
        \
       Wi-Fi Router ---- Internet
        /
       /
    Laptop

The router connects your local devices to a much larger network.

That larger network eventually connects to the global internet.

## Local Network vs Internet

A local network is a smaller private network.

Examples:

- Home Wi-Fi
- School computer lab
- Office network
- Cyber cafe network

The internet is the massive global network that connects many smaller networks together.

That is why the internet is often called:

    A network of networks

## What Is An ISP?

ISP means Internet Service Provider.

Your ISP is the company that gives you access to the internet.

Examples may include:

- Mobile network providers
- Fiber internet providers
- Broadband providers
- Satellite internet providers

Your ISP connects your home, phone, or office network to the wider internet.

Basic journey:

    Your Device → Router → ISP → Internet

Without an ISP or some kind of internet provider, your device may still work locally, but it cannot communicate with online services.

## What Is A Router?

A router is a networking device that directs data between networks.

At home, your router connects your devices to your ISP.

On the wider internet, many routers pass data from one network to another until it reaches the correct destination.

A router is like a traffic controller for data.

It helps decide where packets should go next.

## What Is An IP Address?

An IP address is a unique address used to identify a device or server on a network.

IP means Internet Protocol.

Example style:

    192.168.1.10

or

    8.8.8.8

IP addresses help devices find and communicate with each other.

A simple analogy:

    Home address → identifies a house
    IP address → identifies a device or server on a network

When your browser wants to reach a website, it eventually needs an IP address for the server hosting that website.

## Public IP vs Private IP

A private IP address is used inside a local network.

Example:

    192.168.1.5

A public IP address is used on the internet.

Your home router usually has a public IP address assigned by your ISP.

Devices inside your home may have private IP addresses.

Simplified view:

    Laptop: private IP
    Phone: private IP
    Router: public IP
    Website server: public IP

## What Is Data?

Data is information.

Examples:

- Text
- Images
- Videos
- Audio
- HTML
- CSS
- JavaScript
- JSON
- API responses

When you load a website, your browser receives data from a server.

When you submit a form, your browser sends data to a server.

## What Are Packets?

Data sent over the internet is broken into smaller pieces called packets.

Instead of sending one giant block of data, the internet sends many small packets.

A packet may contain:

- A piece of the data
- Source address
- Destination address
- Ordering information
- Error-checking information

Think of packets like pages of a book sent in separate envelopes.

When they arrive, the receiver puts them back together in the correct order.

## Why Data Is Broken Into Packets

Data is broken into packets because packets make communication more efficient and reliable.

Benefits:

- Large files can travel in smaller pieces.
- Packets can take different routes.
- Lost packets can be resent.
- Networks can handle many users at once.
- Errors are easier to detect and fix.

Example:

When you stream a video, the video data is sent in many packets.

Your device receives those packets, organizes them, and plays the video.

## What Is TCP/IP?

TCP/IP is a set of networking rules that helps devices communicate across the internet.

TCP means Transmission Control Protocol.

IP means Internet Protocol.

Simple explanation:

IP helps data find the destination.

TCP helps ensure data arrives correctly and in order.

TCP is useful when reliability matters.

Examples:

- Loading webpages
- Sending emails
- Downloading files
- API requests

## What Is UDP?

UDP means User Datagram Protocol.

UDP is another communication protocol.

It is faster but less focused on guaranteed delivery.

UDP is often used when speed matters more than perfect delivery.

Examples:

- Live video calls
- Online gaming
- Voice calls
- Streaming scenarios

For beginner web development, HTTP usually runs over TCP.

Later, you may learn about more advanced protocols.

## What Happens When You Open A Website?

Imagine you type:

    example.com

into your browser.

A simplified journey:

    1. Browser checks the website address.
    2. Browser asks DNS for the server IP address.
    3. Browser connects to the server.
    4. Browser sends an HTTP or HTTPS request.
    5. Server sends back a response.
    6. Browser downloads HTML, CSS, JavaScript, images, and other files.
    7. Browser renders the page.

This module will explain these steps in more detail across several lessons.

## The Journey Of A Request

Simplified diagram:

    Browser
       |
       v
    Home Router
       |
       v
    ISP
       |
       v
    Internet Routers
       |
       v
    Website Server
       |
       v
    Response travels back

The process happens very quickly.

Sometimes in milliseconds.

## What Is A Server?

A server is a computer that provides services or resources to other computers.

Examples:

- Web server
- Database server
- File server
- API server
- Email server

When you build a backend application with Node.js, your application can behave like a server.

It waits for requests and sends responses.

## What Is A Client?

A client is a device or program that requests something from a server.

Examples:

- Browser
- Mobile app
- Desktop app
- API testing tool
- Another server

In web development, your browser is often the client.

A backend API is often the server.

## Internet Infrastructure

The internet depends on physical infrastructure.

Examples:

- Fiber optic cables
- Cell towers
- Routers
- Switches
- Data centers
- Undersea cables
- Satellites in some cases

Even though the internet feels invisible, it depends heavily on real physical equipment.

## Fiber Optic Cables

Fiber optic cables send data using light signals.

They can carry huge amounts of data over long distances.

Many countries are connected through undersea fiber optic cables.

When you access a website hosted in another country, your data may travel through cables crossing cities, countries, and oceans.

## Data Centers

A data center is a building filled with servers and networking equipment.

Many websites and applications run from data centers.

Cloud providers operate large data centers around the world.

Examples of things hosted in data centers:

- Websites
- APIs
- Databases
- Cloud storage
- Streaming services
- Email systems

## Why This Matters To Full Stack Developers

Full stack developers build applications that communicate over networks.

Frontend apps send requests.

Backend apps receive requests.

Databases may live on another server.

APIs may call other APIs.

Authentication, payments, file uploads, emails, and dashboards all depend on internet communication.

Understanding the internet helps you debug problems like:

- Website not loading
- API request failing
- DNS not resolving
- Server timeout
- Wrong URL
- CORS error
- SSL certificate issue
- Slow response time

## Practical Example: Visiting A Portfolio Website

When someone visits your portfolio website:

    1. They type the URL.
    2. DNS finds the server.
    3. Browser connects to the hosting provider.
    4. Browser requests the webpage.
    5. Server returns files.
    6. Browser renders the design.
    7. JavaScript may run.
    8. Images and fonts load.
    9. The visitor sees the page.

This entire process depends on internet fundamentals.

## Common Beginner Mistakes

### Mistake 1: Thinking The Internet Is The Same As The Web

The web runs on the internet, but the internet supports many other services too.

### Mistake 2: Thinking Websites Live Inside Browsers

Browsers do not store most websites permanently.

They request website files from servers.

### Mistake 3: Ignoring Network Errors

Network errors often explain why applications fail.

### Mistake 4: Not Understanding URLs

A URL tells the browser where to find a resource.

### Mistake 5: Thinking Servers Are Always Huge Machines

A server can be a powerful data center machine, but your laptop can also run a server during development.

## Exercises

### Exercise 1

Explain the internet in your own words.

### Exercise 2

Explain the difference between the internet and the web.

### Exercise 3

Draw a simple request journey from your browser to a server.

Use this format:

    Browser → Router → ISP → Internet → Server

### Exercise 4

List five things that use the internet but are not necessarily websites.

### Exercise 5

Explain what an ISP does.

### Exercise 6

Explain why data is broken into packets.

### Exercise 7

Explain the difference between a client and a server.

### Exercise 8

Identify the client and server in this example:

    You open YouTube in Chrome.

### Exercise 9

Identify the client and server in this example:

    A React app sends a login request to a Node.js API.

### Exercise 10

Research your current public IP address using a search engine.

Do not save it in a public repo.

Just observe that your network has a public address.

## Mini Lab: Trace A Website Request Conceptually

Choose any website you visit often.

Write a simple explanation of what happens when you open it.

Use this format:

    1. I enter the URL.
    2. The browser needs the server IP address.
    3. DNS helps find the IP address.
    4. The browser sends a request.
    5. The server sends a response.
    6. The browser renders the page.

You do not need to fully understand DNS and HTTP yet.

Those are covered in later lessons.

## Did You Know?

The internet was designed to be resilient. Data can often travel through different routes if one route is unavailable.

## Fun Fact

Many people say "the internet is in the cloud," but the cloud is mostly other people's computers in data centers connected through physical networks.

## Summary

The internet is a global network of connected networks.

It allows devices, servers, applications, and services to communicate.

Data travels across the internet in packets.

Routers help move packets between networks.

ISPs connect users to the wider internet.

Clients request resources.

Servers provide resources.

As a full stack developer, understanding the internet helps you understand websites, APIs, hosting, deployment, debugging, and application architecture.

## References

- https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/How_does_the_Internet_work
- https://www.cloudflare.com/learning/network-layer/what-is-the-internet/
- https://www.cloudflare.com/learning/network-layer/what-is-a-packet/
- https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_domain_name
