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

## Parameters

- **Header**: Metadata about the request, such as the format of the
  response, or the authorization token.
- **Path**: The path to the ressource, which is used to identify the
  ressource (e.g., `/users/123`).
- **Query**: Additional parameters to filter the ressource embeded
  in the URL in the form of [query string](../138/README.md)(e.g.,
  `/users?role=admin`).

## Simple Example

When entering the following URL in `firefox` 
<https://api.restful-api.dev/objects?id=3&id=5&id=10>, we asked the
server to connect to the *objects* ressources, and filter those
with id=[3, 5, 10]. The server will respond with the following JSON.

```json
[
  {
    "id": "3",
    "name": "Apple iPhone 12 Pro Max",
    "data": {
      "color": "Cloudy White",
      "capacity GB": 512
    }
  },
  {
    "id": "5",
    "name": "Samsung Galaxy Z Fold2",
    "data": {
      "price": 689.99,
      "color": "Brown"
    }
  },
  {
    "id": "10",
    "name": "Apple iPad Mini 5th Gen",
    "data": {
      "Capacity": "64 GB",
      "Screen size": 7.9
    }
  }
]
```

## More complex example with CURL



---
<https://stackoverflow.blog/2020/03/02/best-practices-for-rest-api-design/>
<https://restful-api.dev/rest-fundamentals#rest>

