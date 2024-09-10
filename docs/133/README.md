# Architecture of HTTP messages

HTTP is a protocol for fetching ressources. It is the
foundation of data exchange on the web and is based on a
request-response model (a client sends a request to a server,
and the server responds to the request).

HTTP messages (before HTTP/2) are human readable text format. Now they are encapsulates in frames with HTTP/2, and encrypted with HTTPs, although the principle remains the same.

For an in depth explanation of the HTTP protocol, see the mozilla
developer network's
[HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
page.

## Strengths
HTTP is: 
    - simple,
    - stateless (each request is independent of the
previous one)
    - extensible (it can be used for more than
just fetching web pages).

## Overview of a request
The overall architecture of an HTTP request is as follows:

- Method (required) -- E.g., GET
- Path (required) --  E.g., /
- Host (required) -- E.g., developer.mozilla.org
- Protocol version (required) -- E.g., HTTP/1.1
- Headers (optional) -- E.g., User-Agent: Mozilla/5.0
- Body (optional) -- E.g., ressource send for `POST`

The following example is from the [mozilla developer
network's](https://mdn.github.io/shared-assets/images/diagrams/http/overview/http-request.svg)

![HTTP request](./http_request.svg)

## Overview of a response

The overall architecture of an HTTP response is as follows:

- Protocol version (required) -- E.g., HTTP/1.1
- Status code (required) -- E.g., 200
- Status message (required) -- E.g., OK
- Headers (optional) -- E.g., Content-Type: text/html
- Body (optional) -- E.g., fetched source

The following example is from the [mozilla developer
network's](../133/http_response.svg)

## Example using netcast

Using `netcast` utility, it is possible to send raw HTTP request
to a server.

```bash
nc example.com 80
GET / HTTP/1.1
host: example.com
```

This will send a GET request to example.com, and the server will
respond with the content of the root page:

```bash
HTTP/1.1 200 OK
Accept-Ranges: bytes
Age: 578757
Cache-Control: max-age=604800
Content-Type: text/html; charset=UTF-8
Date: Tue, 10 Sep 2024 09:08:07 GMT
Etag: "3147526947+gzip"
Expires: Tue, 17 Sep 2024 09:08:07 GMT
Last-Modified: Thu, 17 Oct 2019 07:18:26 GMT
Server: ECAcc (bsb/27A7)
Vary: Accept-Encoding
X-Cache: HIT
Content-Length: 1256

<!doctype html>... (here come the content of the page)
```

---
<https://developer.mozilla.org/en-US/docs/Web/HTTP>
