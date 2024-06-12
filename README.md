# fetchwrapper

Simple and compact wrapper for JavaScript standard fetch() API.

# Dependency

JavaScript processor you like with `fetch()` implemented.

# Usage

## Overview

```javascript
import {http} from './httpclient.mjs'

await get("https://example.com")
await get("https://example.com", options: {query: {foo: "abc123"}})
await post("https://example.com/a/b/c", {data: 12345}, options: {query: {foo: "abc123"}})
```

## Options

|property|description|
|-------|------------------------|
|`query`|URL Query object|
|`headers`|HTTP Request header (object.)|
|`style`|Request object translation style. If `form` is set, body is translated to url encoded and set content type header. If `through` is set, do not translate. Otherwise, body is translated to JSON string and set content type header.|
|`blob`|If ture, `request()` returns resolved `Response.prototype.blob()`|

# 4xx or 5xx status code

If you got `4xx` or `5xx` response status code, `request()` throws custom exception.
