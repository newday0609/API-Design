# API Content Structure

Organise your API content into the following broad categories:
API documentation consists of two parts:

1. Narrative Content
2. Open API spec files

Both are mandatory, and will be injested and displayed in the `Developer Portal`.

## Narrative Content

* **Introduction**: Include the following:
  * What the API does
  * Who the intended users are
  * What scenarios you would use this API in
  * Any Prerequisites
  * Any useful diagrams:
    * (Optional) Sequence Diagram explaining any particular sequencing of API calls across multiple endpoints.
    * (Optional) Context Diagram - e.g. how the MultiQuote API fits into the context of aggregators acquisition process.

You can include any additional information as applicable.

## OpenAPI spec files

Your OpenAPI should be OpenAPI 3.0 and incluse at least the following properties:

* The path and any required query parameters
* Example requests
* Example responses
* Error Codes

When you are describing the parameters, you must include at least the parameter name, and a meaningful description.

|Parameter Name |Format | Description  |
|------------------------|-----------|-------------------|
| Name | Text| Name of the credit applicant. |
|Contact Number | String | Include examples, if required. For example: _The contact number must start with '07'; for example, 07458847898._|

**Avoid redundent descriptions** - for example "Name" = "The Name". Rather ommit the description field than waste space.

For information on the formats in which you must generate the API content, refer to [API Document Format](/DocumentationGuidelines/APIDocumentFormat.md). For information on the process that you must follow to provide the content to the Developer Portal team, refer to the [Document Publication Process](./DocumentPublicationProcess.md).
