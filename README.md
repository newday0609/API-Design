# API-Design

The goal of this document is to support the advancement of the [RESTful API Maturity model](reference/MaturityModel.md).

RESTful API design is a practice that all RESTful based API should follow, there are options available within for engineers to choose from, giving allowances for differing requirements. These are based on our own engineering experience and various industry guidelines.

## Contents

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [API-Design](#api-design)
  - [Contents](#contents)
  - [Disclaimer & Intended Audience](#disclaimer-intended-audience)
  - [Principles](#principles)
  - [API Standards](#api-standards)
  - [Guidelines](#guidelines)
  - [Contributing](#contributing)

<!-- /code_chunk_output -->

## Disclaimer & Intended Audience

Please note, this document is **not intended to be used for non-REST based APIs**.

There will be categories of APIs that require different implementation details than outlined here, such as GraphAPIs (they're by definition, not REST based), or that adhear to another protocol or architectural style.

**By default, we will assume that the vast majority of APIs we produce for the consumption of other teams, partners, or the public are REST based and will adhere to the following principles.**

If you are producing APIs for your specific application only (for example, a Backend-for-Frontend API), it's acceptible to deviate from these standards to serve your applications needs, however, any API that doesn't meet the standards here shall **never** be used for any other purpose.

## Principles

- [General Design Principles](reference/DesignPrinciples.md)

## API Standards

- [Urls, Verbs, and Response Codes](standards/UrlsVerbsAndResponseCodes.md)
- [Versioning](standards/Versioning.md)
- [Security](standards/Security.md)
- [PCI Data](standards/PCIData.md)

## Guidelines

Work in progress set of guidelines for REST APIs.

- [Status Codes guidelines](guidelines/StatusCodes.md)
- [Errors: ProblemDetails](guidelines/ProblemDetails.md)

## Contributing

Please open pull requests to this standard to initate debate and changes.

[A list of authors and contributors is avilable here](AUTHORS.md).
