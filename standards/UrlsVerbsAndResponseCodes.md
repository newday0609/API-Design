# URLs, Verbs, and Response Codes

## Naming Standards

**You must have consistency locally within your system for pluralisation**, so no API on the same sub-domain that has multiple conventions.

If you include the type in the variable name it must represent the underlaying type.

**Must keep URLs verb free** (e.g. /account/getcards is incorrect, a HTTP GET to /account/cards is correct)

## Casing

### Must make sense without using a casing strategy

Assume case insensitive.

Examples:

    /collection-records/1
    /collectionrecords/1

### Must use camelCase for query parameters

Example: /collectionrecords?sortBy=Date

## Resources

### Must Identify resources and sub-resources via path segments if sub-resources are not top-level resources

Examples:

    /Orders/2/Items/1

### Must consider separate routes if the sub-resource can be defined as top-level resource

Examples:

    /Customers/5
    /Orders/23

    instead of

    /Customers/5/Orders/23

## Verbs

The appropriate verbs should be used when creating the API.

**The verb should not exist in the URI or another form of the verb** (e.g. no need to write “SAVE” in URI when the verb is a POST or PATCH).

The available verbs are listed in the RFC 261 specification in section 9.1.2, but for completeness, are:

- GET
- POST
- PUT
- DELETE
- PATCH
- HEAD
- OPTIONS

## Nouns

See: https://newdaycards.atlassian.net/wiki/spaces/ENG/pages/2403926249/Glossary+of+Nouns

## Response Codes

Each request to the API should respond with the appropriate HTTP response code as defined in RFC 2616 Section 10:

[RFC 2616 - Hypertext Transfer Protocol -- HTTP/1.1](https://datatracker.ietf.org/doc/html/rfc2616#section-10)

We must not repurpose response codes for other purposes than originally intended.
