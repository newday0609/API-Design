# Mandatory Endpoints

## Internal Use Only

These endpoints are all required to be implemented by all APIs.They are internal only, and should not be exposed over APIM, or in external documentation.

### Heart Beat

Each API **MUST** have a heart beat endpoint at `/heartbeat` that returns a 200 OK response. This is only concerned with availability, and not downstream depenedencies.

### Health Check

Each API **MUST** have a health check endpoint at `/healthcheck` that returns a 200 OK response.

API health checks **MAY** contain more detailed and granular embedded checks that verify downstream dependencies.

## External Use

### Open API

Each API **MUST** expose an OpenAPI specification at `/openapi.json` or `/swagger.json`.

We currenty intend to use `OpenAPI tags` to include and expose APIs to our partners and consumers.

APIs can be tagged wholesale - where a tag is applied to an entire `API`, or on an endpoint-by-endpoint basis, for more granular control. By default, untagged `APIs` will only be visibile in the `API portal` in pre-UAT environments.

Applying the following tags to endpoints or entire `APIs` does the following:

- no tag: `API` is visible in the `Dev API portal`
- `beta`: `API` is visible in the `UAT API portal`
- `internal`: `API` is visible in the `UAT API portal`, and to NewDay teams logged in to the `Production API portal`. `API` is not visible to NewDay partners.
- `public`: `API` is visible in the `Production API portal`.

APIs that do not meet the basic requirements of the `API Checklist` **MUST NOT** be promoted to `internal` or `public` before being reviewed.
