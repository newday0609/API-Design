# API Documentation Guidelines

---

These are our guidelines for writing API documentation.
It's important that our docs are **simple**, **easy to follow**, and **consistent**.

They must be suitable for both native and non-native English speakers.

## Table of Contents

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [API Documentation Guidelines](#api-documentation-guidelines)
  - [Table of Contents](#table-of-contents)
  - [Required Documents](#required-documents)
  - [The User Guide Content](#the-user-guide-content)
  - [OpenAPI spec files](#openapi-spec-files)
  - [The Publication Process](#the-publication-process)
  - [Appendix A - Writing Style](#appendix-a-writing-style)

<!-- /code_chunk_output -->

## Required Documents

We require the following documents to be provided to the Developer Portal team:

1. A user-guide introduction, written in `markdown`.
2. An Open API 3.0 spec file describing your APIs.

These two artifacts will be combined and ingested into the Developer Portal.

## The User Guide Content

This **introduction** should include the following:

* What the API does
* Who the intended users are
* What scenarios you would use this API in
* Any Prerequisites
* Any useful diagrams:
  * **(Optional)** Sequence Diagram explaining any particular sequencing of API calls across multiple endpoints.
  * **(Optional)** Context Diagram - e.g. how the MultiQuote API fits into the context of aggregators acquisition process.

You can (obviously!) include any additional information as applicable.

Write the content in any editor [that supports Markdown format](https://www.markdownguide.org/cheat-sheet).

Provide this file as `index.md`.

## OpenAPI spec files

Your spec file should be OpenAPI 3.0 and incluse at least the following properties:

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

**It is expected that you use language provided tooling to generate these OpenAPI specs from your code.**

## The Publication Process

For information on the process that you must follow to provide the content to the Developer Portal team, refer to the [Document Publication Process](./DocumentPublicationProcess.md).

## Appendix A - Writing Style

We have a [Style Guide](./StyleGuide.md) that you can use to help write your documentation. It includes guidance on tone of voice, capitalisation, and other written style.

In addition to the style guide, consider the following when writing:

* **Think about the reader**: When you write, consider the following questions:
  * Why will they read this content?
  * Does your documentation answer the most commonly asked questions?
  * How long did it take to find the information they are looking for?

* **Write an essay plan**: It's easier to write an outline of your documentation first, and then revise it over subsequent drafts, expanding on your points. This will improve the flow of the content.

* **Keep your sentences short**: It is  difficult to understand long sentences. Write simple sentences that are easier to follow.

* **Punctuation is important**: Punctuation can alter the meaning of your content - make sure you write "let's eat, kids", not "let's eat kids"!

* **Include a Glossary**: Explain the terms and their definitions, if required. **[Ed: We should maintain a centralised glossay in the dev portal]**

