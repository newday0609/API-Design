# API Maturity Model

---

## Level 1

Plain OLD XML or other weird API formats, zero-consistency from API to API, single endpoint API designs, chaos, incoherent response documents

## To Progress

- Either
  - Migrate to JSON as a transport format.
  - Split up single "RPC endpoints" into multiple different paths.

## Level 2

Multiple URI based resources, single verbs, consistency in format and structure of URIs (consistent URL patterns and conventions around pluralisation and naming) within your own service (if referencing global resources, they are to the defined global standard), basic swagger / some other auto-doc support accessible to humans

## Level 3 - 🎯 TARGET

Interaction with URI resources using multiple and appropriate HTTP verbs, response documents following internally consistent conventions, resource-oriented APIs, an approach to versioning or changing APIs

## Level 4

Interactive documentation with human-consumable information, API docs present in org-wide API management solution, adheres to companywide conventions

## Level 5

Version infinite API design, forwards compatibility, Hypertext as the engine of application state (HATEOAS)
