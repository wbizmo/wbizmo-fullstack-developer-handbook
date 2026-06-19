# Lesson 05: How Websites Actually Load

## Learning Objectives

By the end of this lesson, you should understand the full journey from typing a URL to seeing a webpage.

## The Big Picture

When you enter a website address, many things happen quickly.

Example:

    https://example.com

The browser does not magically know where the website is.

It must resolve the domain, connect to the server, request files, download resources, and render the page.

## Step 1: User Enters URL

You type a URL into the browser.

Example:

    https://example.com/about

The browser reads:

- Protocol
- Domain
- Path

Protocol:

    https

Domain:

    example.com

Path:

    /about

## Step 2: DNS Lookup

The browser needs the server IP address.

DNS translates:

    example.com

into an IP address.

## Step 3: Connection

The browser connects to the server.

For HTTPS, secure encryption is established.

## Step 4: HTTP Request

The browser sends a request.

Example:

    GET /about

The server receives the request.

## Step 5: Server Response

The server sends a response.

The response may include:

- HTML
- Status code
- Headers
- Other data

## Step 6: Browser Reads HTML

The browser reads the HTML document.

HTML gives the page structure.

## Step 7: Browser Finds More Resources

The HTML may reference:

- CSS files
- JavaScript files
- Images
- Fonts
- Videos

The browser sends more requests for those resources.

## Step 8: CSS Is Applied

CSS controls presentation.

Examples:

- Colors
- Layout
- Spacing
- Typography
- Responsiveness

## Step 9: JavaScript Runs

JavaScript adds behavior.

Examples:

- Dropdown menus
- Form validation
- API requests
- Interactive dashboards

## Step 10: Page Is Rendered

The browser combines:

- HTML structure
- CSS styling
- JavaScript behavior
- Images and fonts

Then it displays the final page.

## Simplified Flow

    Enter URL
    DNS Lookup
    Connect To Server
    Send HTTP Request
    Receive HTML
    Download CSS, JS, Images
    Render Page

## Why Websites Can Be Slow

A website may be slow because of:

- Large images
- Too many JavaScript files
- Slow server
- Poor hosting
- Bad network
- Too many third-party scripts
- Unoptimized fonts
- Large CSS files

## Developer Tools

Browsers include developer tools.

You can inspect:

- HTML
- CSS
- Console errors
- Network requests
- Performance
- Storage

In Chrome or Edge:

    Right click → Inspect

or press:

    F12

## Network Tab

The Network tab shows requests made by the browser.

You can see:

- Files loaded
- Status codes
- Response times
- Request size
- Headers

This is extremely useful for debugging.

## Common Mistakes

- Thinking one page equals one request
- Ignoring images and fonts
- Forgetting that JavaScript can request more data later
- Not checking the browser console
- Not checking the Network tab

## Exercises

1. Open any website.
2. Right-click and inspect.
3. Open the Network tab.
4. Refresh the page.
5. Observe how many files load.
6. Find one HTML request.
7. Find one CSS or JS request.
8. Find one image request.
9. Identify one status code.
10. Explain the full loading process in your own words.

## Summary

A website loads through a sequence of network and browser operations.

The browser resolves the domain, connects to a server, sends requests, downloads resources, and renders the page.

Understanding this process makes HTML, CSS, JavaScript, APIs, performance, and debugging easier.
