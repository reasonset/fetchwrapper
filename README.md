# fetchwrapper

Simple and compact wrapper for JavaScript standard fetch() API.

# Dependency

JavaScript processor you like with `fetch()` implemented.

# Usage

## Overview

```javascript
import {http} from './httpclient.mjs'

await http.get("https://example.com")
await http.get("https://example.com", {query: {foo: "abc123"}})
await http.post("https://example.com/a/b/c", {meow: 12345}, {query: {foo: "abc123"}})
```

## API

### http

```
http.get(URL[, options])
http.post(URL[, data[, options]])
http.put(URL[, data[, options]])
http.delete(URL[, options])
```

### Use `HTTPClient` class manually

```
HTTPClient(url, body, options) => object
HTTPClient.prototype.request() => object|string|null
```

## Options

|property|description|
|-------|------------------------|
|`query`|URL Query object|
|`headers`|HTTP Request header (object.)|
|`style`|Request object translation style. If `form` is set, body is translated to url encoded and set content type header. If `through` is set, do not translate. Otherwise, body is translated to JSON string and set content type header.|
|`blob`|If ture, `request()` returns resolved `Response.prototype.blob()`|
|`method`|HTTP request method. This option isn't needed on `http` methods.|

# 4xx or 5xx status code

If you got `4xx` or `5xx` response status code, `request()` throws custom exception.
