# API Errors Samples

## Sample Types

| Status | Type | Title | Sample |
| ------ | ---- | ----- | ------ |
| 400 Bad Request | newday:error:validation | Your request parameters or fields contain validation errors. | [Validation](#validation) |
| 404 Not Found | newday:error:missing | The resource requested does not exist. | [Missing](#missing) |
| 500 Internal Server Error | newday:error:unavailable | Service can't process the request right now. e.g. one of the dependencies is unavailable. | [Unavailable](#unavailable) |

## Sample Generic Errors

| Status | Sample |
| ------ | ------ |
| 401 Unauthorized | [Unauthorized](#unauthorized) |
| 403 Forbidden | [Forbidden](#forbidden) |
| 404 Not Found | [Not Found](#generic-not-found) |
| 415 Unsupported Media Type | [Unsupported Media Type](#unsupported-media-type) |
| 500 Internal Server Error | [Internal Server Error](#generic-internal-server-error) |

## Examples

### Bad Request

#### Validation

```text
HTTP/1.1 400 Bad Request
Content-Type: application/problem+json
```

```json
{
    "type": "newday:error:validation",
    "invalidValues": [
        {
            "name": "age",
            "reason": "must be a positive integer"
        },
        {
            "path": "$.items[0].color",
            "reason": "must be 'green', 'red' or 'blue'"
        }
    ]
}
```

### Unauthorized

```text
HTTP/1.1 400 Bad Request
Content-Type: application/problem+json
```

```json
{
}
```

### Forbidden

```text
HTTP/1.1 403 Forbidden
Content-Type: application/problem+json
```

```json
{
}
```

### Not Found

#### Generic Not Found

```text
HTTP/1.1 404 Not Found
Content-Type: application/problem+json
```

```json
{
}
```

#### Missing

```text
HTTP/1.1 404 Not Found
Content-Type: application/problem+json
```

```json
{
    "type": "newday:error:missing"
}
```

### Unsupported Media Type

```text
HTTP/1.1 415 Unsupported Media Type
Content-Type: application/problem+json
```

```json
{
}
```

### Internal Server Error

#### Generic Internal Server Error

```text
HTTP/1.1 500 Internal Server Error
Content-Type: application/problem+json
```

```json
{
}
```

#### Unavailable

Service can't process the request right now. e.g. one of the dependencies is unavailable

```text
HTTP/1.1 500 Internal Server Error
Content-Type: application/problem+json
Retry-After: 2
```

```json
{
    "type": "newday:error:unavailable",
}
```

In integration environment it could be more specific, returning list of dependecies that have failed and the `ProblemDetails` isntance of the error returned by each one.

```text
HTTP/1.1 500 Internal Server Error
Content-Type: application/problem+json
Retry-After: 2
```

```json
{
    "type": "newday:error:unavailable",
    "dependencies": [
        {
            "name": "foo",
            "details": {
                "type": "newday:error:unavailable"
            }
        }
    ]
}
```
