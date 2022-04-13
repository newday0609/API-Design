# Mandatory Endpoints

## Health Check

Each API **MUST** have a health check endpoint at `/health` that returns a 200 OK response.

API health checks **MAY** contain more detailed and granular embedded checks that verify downstream dependencies.

## Open API

Each API **MUST** expose an OpenAPI specification at `/openapi.json` or `/swagger.json`.
