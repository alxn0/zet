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

## Considerations in the context of HTTP communication

1. **Ressources**: Everything is a ressource, and they are represented
    by Uniform Ressource Identifiers (URIs). On the web, these are accessed
    through URLs.
2. **Stateless**: Each request is independent, and all the information
   necessary for the resquest is provided by the client. The server
   does not store any information about the client or the request.
3. **Cacheable**: The server can specify if the response can be cached
   by the client, which improve performance. For example, the server
   can cached the response for a given time, and the client can use
   the cached response until it expires to optimize further requests.
4. **HTTP standard**: REST APIs are called using the HTTP protocol. 
    - *Commands* : This makes the API easy to use and understand, intuitively 
      mapping the CRUD operations (create, read, update,
      delete) to the HTTP verbs (POST, GET, PUT, DELETE). 
    - *error handling* is also communicate through the HTTP status codes.
    - *Content negotiation* is used to specify the format of the
      response, such as JSON or XML.
    - *Authorization* is also handled through the HTTP headers with 
    tokens or API keys.

## Example 



