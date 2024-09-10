# REST API

## What is it?
REST, for REpresentational State Transfer, is an API architecture. While
REST APIs is not restricted to a given protocol, they are mainly called
over HTTPs. 

It was first develop in 2000 by Roy Fielding, in his [doctoral
dissertation](./fielding_dissertation.pdf), to simply the design of
HTTP APIs, and make them more scalable.

Nowadays, they are the most common way to expose APIs (endpoint) 
over the internet.

A restful service is a service that communicate through
a REST API.

## Considerations
1. Standardize (simple)
2. Stateless (Scalable)
3. Caching (high performance)

## How does it work in an HTTP context?

REST APIs are represented as URLs, and they are called using the
HTTP methods (GET, POST, PUT, DELETE).


```bash
curl -X GET https://api.example.com/users
```
