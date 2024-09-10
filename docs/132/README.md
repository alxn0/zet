# HTTP server (web server) 

A web server is a software designed to serve HTTP content. It listens on a port
for incoming requests and sends back responses. Common web servers are
Apache and NGINX, although Caddy offers a more modern approach for
simple and secure webserver.

The actual [HTTP messages](../133/README.md) are text based that
follows the [RFC 2616](https://www.rfc-editor.org/rfc/rfc2616).

Web browsers does HTTP requests when we type a URL into the
address bar. It send an HTTP request to the server 
and display the HTTP responses.

HTTP based APIs can also be used to interact with web servers.
A common example is the [REpresentation State Transfer API] (a.k.a. REST)
architecture, which is the most common approach to build web-based APIs
for backend services.

Web server relies on [TCP/IP protocol](../135/README.md) to communicate with clients.
The server listens on a port for incoming requests and sends back
responses.

[Application server](../136/README.md) can also be used in conjunction with web server
to run server-side code and generate dynamic content. The web server
receives the request from the clients and forwards it to the 
application server. The application server processes the request and
sends back the response to the web server, which in turn sends it back
to the client. In this framework, web server can also be used only as
[reverse proxy](../137/README.md), a gateway that forward requests 
to multiple application servers.



---










