# Versioning

All our API’s should follow a versioning protocol and avoid minor versioning if possible. Only major breaking changes should result in a new version, however, we expect developers to minimise the need for versioning by practicing good “addition” to API’s rather than creating a new version for every change. If items need to be made obsolete later it should be only removed when there is a major version change. All changes should be documented in the project “Change Log”.

There is no need to be able to request different version of content via requesting the required content type in the headers as we currently only support JSON.

Versioning ideally could be changed via the URI rather than headers if not using HATEOAS due to the difficultly of some front ends to support this method (e.g. JSONP / CORS) and the complexity / overhead of adding additional headers, the goal is to keep things simple. We are not specifying explicitly which you should use but you should aim to choose between defining the version via the URI if possible or the headers if not (e.g. in the use of HATEOAS) or to be able to use headers to override the current version.

## When not to Version

    Read: “How we aim to extend our APIs”.

- Adding new API resources
- Adding new optional request parameters to existing API methods
- Adding new properties to existing API responses
- Changing the order of properties in existing API responses
- Changed technology
- Changing the length or format of opaque strings, such as object IDs, error messages, and other human-readable strings

## Definition of a Breaking Change

    Read: “If you’re doing this - strongly consider an alternative”.

Changes to the contract of an API are considered a breaking change. Changes that impact the backwards compatibility of an API are a breaking change.

Teams may define backwards compatibility as their business product line needs require. These terms must be defined so clients understand.

Our guide on what broadly constitutes a breaking change is as follows:

- Removing or renaming APIs or API parameters / arguments
- Removing or renaming responses fields
- Changes in behaviour for an existing API; including default parameter / argument behaviour
- Changes in casing of property names, at any point in the object graph (:warning: beware if assigning objects directly based on responses from other services)
- Changes in Error Codes

Anything that would violate the *Principle of Least Astonishment*.
