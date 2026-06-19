# Lesson 03: DNS, Domains and Hosting

## Learning Objectives

By the end of this lesson, you should understand domains, DNS, hosting, IP addresses, and how a human-friendly website name points to a real server.

## What Is A Domain Name?

A domain name is a human-readable website address.

Examples:

- google.com
- github.com
- vercel.app

Humans prefer names. Computers need IP addresses.

## What Is DNS?

DNS means Domain Name System.

DNS translates domain names into IP addresses.

Simple idea:

    Domain name → DNS → IP address

Example:

    example.com → DNS lookup → server IP address

DNS is often called the phonebook of the internet.

## Why DNS Exists

Without DNS, users would need to remember IP addresses instead of names.

That would be difficult.

Instead of typing:

    142.250.190.14

you type:

    google.com

## What Is Hosting?

Hosting means placing your website or application on a server so people can access it online.

Examples of hosting platforms:

- Vercel
- Netlify
- Render
- Railway
- DigitalOcean
- AWS
- Azure
- Google Cloud

## Domain vs Hosting

Domain:

    The name people type.

Hosting:

    The server where the site lives.

Example:

    Domain: mysite.com
    Hosting: Vercel server

## DNS Records

DNS records are instructions for a domain.

Common records:

A record:
    Points a domain to an IPv4 address.

AAAA record:
    Points a domain to an IPv6 address.

CNAME:
    Points one domain name to another domain name.

MX:
    Mail server records.

TXT:
    Text records often used for verification and security.

## Real Deployment Example

If you deploy a portfolio to Vercel, Vercel hosts the site.

If you connect a custom domain, DNS tells browsers where that Vercel-hosted site is.

## Common Mistakes

- Buying a domain but not setting DNS
- Deploying a site but not connecting the domain
- Confusing hosting with domain registration
- Expecting DNS changes to work instantly
- Editing the wrong DNS record

## DNS Propagation

DNS changes can take time to update globally.

This delay is called propagation.

Sometimes changes work in one country or network before another.

## Exercises

1. Explain DNS in your own words.
2. Explain the difference between domain and hosting.
3. Name three hosting platforms.
4. Name three DNS record types.
5. Explain why DNS propagation can delay website setup.

## Summary

Domains are human-friendly names. DNS maps names to server addresses. Hosting makes websites available online.
