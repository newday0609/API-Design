---
PublicationReady: true
ForExternalPublication: true
---

# Introduction

========================================

This section dileneates a conceptual understanding about the MultiQuote API —— what is the function of the API, how is your business benefitted, and how the API fits into the credit acquisition workflow.

## Intended Audience

This API is for the aggregators.
If you identify yourself with any of the following user role, this information is relevant for you:

* Business Analyst/Business owner
* Developer/Technical resource  

## Description

The MultiQuote API provides a credit applicant with real time quotation on appropriate NewDay credit products. Hence, this API enables your business to extend real time credit facility to your applicants.
The API performs the following:  

1. You provide an applicant's details to the MultiQuote API.  
2. The API validates the applicant's information.  
3. It selects the specific suite of NewDay credit products that are applicable to your business, and responds with a quotation for each product. The MultiQuote API returns any of the following response:  
    * **Pre-approved**: The applicant is approved to apply for NewDay credit.
    * **Referred**: The applicant cannot be guaranteed of any credit facility. In this scenario, the applicant needs to provide further information for credit acceptance.
    * **Declined**: The application for availing NewDay credit is rejected.

> **Note** Credit quotation for each product mentions the Annual Percentage Rate (APR) of a product and the maximum credit limit allowed to the applicant.
|-|-|

## Benefits

* **Instant credit decision**: The API provides credit quotation on each appropriate NewDay product, which enables an applicant to instantly apply for credit.  
* **Straight forward decision**: The API responds with binary decisions — whether the applicant is accepted to apply for credit, needs to provide with additional information, or is rejected.
* **APR and credit limit**: The API response mentions the APR of a NewDay product and the maximum credit limit allowed to your applicant.

>**Note** If you are procuring Open Banking consent from your applicants, NewDay will support you in your initiative with using Open Banking data. In fact, this process enhances an applicant's chance of being approved for NewDay credit.
|-|-|

## MultiQuote API in the Acquisition Workflow

The following illustration explains how the MultiQuote API interfaces with your business to provide credit to your user:

![MultiQuote API Workflow](./MultiQuote%20API%20Workflow.png "MultiQuote API Workflow")
