# API Errors Samples

## Sample Types

| Status | Type | Title | Sample |
| ------ | ---- | ----- | ------ |
| 400 Bad Request | newday:error:validation | Your request parameters or fields contain validation errors. | [Validation](#Validation) |

## Sample Generic Errors

| Status | Sample |
| ------ | ------ |
| 401 Unauthorized | [Unauthorized](#Unauthorized) |
| 403 Forbidden | [Forbidden](#Forbidden) |
| 415 Unsupported Media Type | [Unsupported Media Type](#unsupported-media-type) |

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
            "name": "color",
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

### Unsupported Media Type

```text
HTTP/1.1 415 Unsupported Media Type
Content-Type: application/problem+json
```

```json
{
}
```
