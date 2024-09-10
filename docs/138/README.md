# Query string

Simply a part of a [URL](../0/README.md) that contains parameters with
assigned values.

For example, in the URL
<https://api.openalex.org/authors/A5023888391?select=id,display_name,orcid>, information
on authors `A5023888391` is requested, and the query string
`select=id,display_name,orcid` is used to specify that only the `id`,
`display_name`, and `orcid` fields should be returned.

Therefore, <https://api.openalex.org/authors/A5023888391> is the API
endpoint, and `select=id,display_name,orcid` is the query string passed
to filter the response.

Also the `?` character is used to separate the endpoint from the query
string.

Multiple query parameters can be passed by separating them with the `&`

For example, <https://api.openalex.org/authors?per-page=50\&page=2>
get he second page of authors results, with 50 results returned per
page.

**There is no standard for query strings, and each API can have its own
query string parameters.**

---
<https://en.wikipedia.org/wiki/Query_string>

