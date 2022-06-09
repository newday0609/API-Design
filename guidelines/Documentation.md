# API Documentation Guidelines

---

These are our guidelines for writing API documentation.
It's important that our docs are **simple**, **easy to follow**, and **consistent**.

They must be suitable for both native and non-native English speakers.

## Table of Contents

- [API Documentation Guidelines](#api-documentation-guidelines)
  - [Required Documents](#required-documents)
  - [The User Guide Content](#the-user-guide-content)
    - [Writing Style](#writing-style)
  - [OpenAPI spec files](#openapi-spec-files)
  - [Document Publication Process](#document-publication-process)
    - [Adding Publication Front Matter](#adding-publication-front-matter)
    - [Opening a PR to the Content Repository](#opening-a-pr-to-the-content-repository)

## Required Documents

We require the following documents to be provided to the Developer Portal team:

1. A **user-guide introduction**, written in `markdown`.
2. An **Open API 3.0 spec file** describing your APIs.

These two artifacts will be combined and ingested into the Developer Portal.

## The User Guide Content

This **introduction** should include the following:

- What the API does
- Who the intended users are
- What scenarios you would use this API in
- Any Prerequisites
- Any useful diagrams:
  - **(Optional)** Sequence Diagram explaining any particular sequencing of API calls across multiple endpoints.
  - **(Optional)** Context Diagram - e.g. how the MultiQuote API fits into the context of aggregators acquisition process.

You can (obviously!) include any additional information as applicable.

Write the content in any editor that supports Markdown format. If you need additional guidance on Markdown, please refer to the [Markdown Cheatsheet](https://www.markdownguide.org/cheat-sheet).

Provide this file as `index.md`. Refer to the [MultiQuote API introduction](./Example-User-Guide.md) as an example.

>**Note** The diagram included in the example file is not the final product and will soon be replaced.

### Writing Style

We have a [Style Guide](./StyleGuide.md) that you can use to help write your documentation. It includes guidance on tone of voice, capitalisation, and other written style.

In addition to the style guide, consider the following when writing:

- **Think about the reader**: When you write, consider the following questions:
  - Why will they read this content?
  - Does your documentation answer the most commonly asked questions?
  - How long did it take to find the information they are looking for?

- **Write an essay plan**: It's easier to write an outline of your documentation first, and then revise it over subsequent drafts, expanding on your points. This will improve the flow of the content.

- **Keep your sentences short**: It is  difficult to understand long sentences. Write simple sentences that are easier to follow.

- **Punctuation is important**: Punctuation can alter the meaning of your content - make sure you write "let's eat, kids", not "let's eat kids"!

- **Include a Glossary**: Explain the terms and their definitions, if required. **[Ed: We should maintain a centralised glossay in the dev portal]**

## OpenAPI spec files

Your spec file should be OpenAPI 3.0 and incluse at least the following properties:

- The path and any required query parameters
- Example requests
- Example responses
- Error Codes

When you are describing the parameters, you must include at least the parameter name, and a meaningful description.

|Parameter Name |Format | Description  |
|------------------------|-----------|-------------------|
| Name | Text| Name of the credit applicant. |
|Contact Number | String | Include examples, if required. For example: _The contact number must start with '07'; for example, 07458847898._|

**Avoid redundant descriptions** - for example "Name" = "The Name". Rather ommit the description field than waste space.

**It is expected that you use language provided tooling to generate these OpenAPI specs from your code.**

## Document Publication Process

Documentation publication process involves adding `front matter` to your `markdown` files and inserting specific values in the OpenAPI specs. To add your products `APIs` into the portal, you need to:

1. Add the correct `Publication Front Matter` in the markdown file.
2. Add values to the OpenAPI spec.
3. Open a `PR` to the [Documentation Repository](https://github.com/NewDayCards/NewDay.Docs.DevPortal.Content) with your `markdown` and `Open API Spec` files.

### Adding Publication Front Matter

`Front Matter` is content that appears at the top of your `markdown` files in the form:

```md
---
some-bool: true
some-string: "some value"
---
# Regular Markdown Content Here

This file contains front-matter
```

Our publication process requires two values:

- `pub-ready` - This is a boolean value that indicates whether the file is ready to be published. **true** will be published in the `production` environments, while **false** will be published to the `UAT`.
- `external-ready` - This is a boolean value that indicates whether the content should be available on the **public** or the **internal** portal.

For a publicly accessible API, your `markdown` doc should look like this:

```md
---
pub-ready: true
external-use: true
---
# Xyz API

The `Xyz` API is a...
```

### Adding Values to OpenAPI Specification

Add the following values to the Swagger files (at each endpoint level) in JSON format:

```{
  "x-pub-settings": {  
    "pub-ready": true,
    "external-use": true
  }
}
```

- `x-newday-pub-ready` if set to "True", the OpenAPI spec will be published in the production environment; otherwise, if set to "False", it will be published in the UAT.  
- `x-newday-external-ready` if set to "True", the OpenAPI spec will be published in the external Developer Portal; otherwise, if set to "False", it will be published in the internal site.

### Opening a PR to the Content Repository

The Developer Portal ingests content from the [Documentation Repository](https://github.com/NewDayCards/NewDay.Docs.DevPortal.Content).

In order to publish your documentation, you'll need to open a pull request. You need to add your content to a subdirectory of the `apiContent` directory.

1. Fork and clone the repository.
2. Create a directory under `apiContent` for your `API`.
3. Add your `index.md` documentation file.
4. Add your `openapi.json` file.
5. Open a pull request adding **Deb Dutta Das** and **David Whitney** as reviewers.
    Content will be revised and merged through discussion on the PR.
