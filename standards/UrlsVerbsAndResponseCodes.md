# URLs, Verbs, and Response Codes

#### TL;DR

- Use standard HTTP verbs
- Use human readable URLs
- Use pluralised entity names in URLs (/people/1 instead of /person/1)
- Kebab case, and lowercase entity names in URLs (/collection-records instead of /collectionrecords)

While a few of the above TL;DR decisions have subjective answers on either side, we should try to just pick one where possible to avoid yak shaving (especially when it comes to plural/singular entity names).

## Naming in Urls

**You MUST must have consistency locally within your system for pluralisation**, so no API on the same sub-domain that has multiple conventions.

If you include the type in the variable name it must represent the underlaying type.

**You MUST keep URLs verb free** (e.g. /accounts/123/getcards is incorrect, a HTTP GET to /account/123/cards is correct)

**You SHOULD use pluralised entity names in URLs** (e.g. /people/1 instead of /person/1)

## Casing

### MUST make sense without using a casing strategy

Assume case insensitive.

Examples:

    /collection-records/1
    /collectionrecords/1

### MUST use camelCase for query parameters

Example: /collectionrecords?sortBy=Date

### HTTP headers use Capitalized-Hyphenated-Terms

Any HTTP headers are the exception and SHOULD use standard HTTP convention of Capitalized-Hyphenated-Terms.

## Resource Design

### Split resources where possible

Multiple top level resources for aggregate roots are more useful to callers.

Examples:

    /customers/5
    /orders/23

    instead of

    /customers/5/orders/23

### Must Identify resources and sub-resources via path segments if sub-resources are not top-level resources

If sub-resources are required, use the path segments to indiciate them.

Examples:

    /orders/2/items/1

### Use summary objects or lists for collections of referenced resources

    /customers/1/orders -> returns summary of orders
    /orders/1 -> returns full order objects

Summary objects MUST contain at least the URI of the full resource, and it's ID.
Summary objects MAY contain other properties, but they MUST be consistent with the full resource.

## HTTP Verbs and Methods

HTTP methods are frequently referred to as the HTTP verbs.
The appropriate verbs should be used when creating the API.

**The verb should not exist in the URI or another form of the verb** (e.g. no need to write “SAVE” in URI when the verb is a POST or PATCH).

The available verbs are listed in the RFC 261 specification in section 9.1.2.

Operations MUST use the proper HTTP methods whenever possible, and operation idempotency MUST be respected.

Borrowed from [Microsoft REST API fundamentals](https://github.com/microsoft/api-guidelines/blob/vNext/Guidelines.md#74-supported-methods), the following should be respected:

Method  | Description                                                                                                                | Is Idempotent
------- | -------------------------------------------------------------------------------------------------------------------------- | -------------
GET     | Return the current value of an object                                                                                      | True
PUT     | Replace an object, or create a named object, when applicable                                                               | True
DELETE  | Delete an object                                                                                                           | True
POST    | Create a new object based on the data provided, or submit a command                                                        | False
HEAD    | Return metadata of an object for a GET response. Resources that support the GET method MAY support the HEAD method as well | True
PATCH   | Apply a partial update to an object                                                                                        | False
OPTIONS | Get information about a request; see below for details.                                                                    | True


## Nouns

Stick to business-wide terminology for common nouns.

See: https://newdaycards.atlassian.net/wiki/spaces/ENG/pages/2403926249/Glossary+of+Nouns

## Response Codes

Each request to the API should respond with the appropriate HTTP response code as defined in RFC 2616 Section 10:

[RFC 2616 - Hypertext Transfer Protocol -- HTTP/1.1](https://datatracker.ietf.org/doc/html/rfc2616#section-10)

We must not repurpose response codes for other purposes than originally intended.
