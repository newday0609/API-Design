---
pub-ready: true
external-use: true
---

# Introduction

========================================

You can perform an eligibility check to verify whether the applicant's credit score meets the requirements for availing NewDay credit. This is a soft check and it does not impact the applicant's credit history; it is a preliminary verification that minimises chances of rejection during the actual application process, which involves hard check of the applicant's credit history.

## Intended Audience

This API is for the aggregators.
If you identify yourself with any of the following user role, this information is relevant for you:

* Business Analyst/Business owner
* Developer/Technical resource  

## Description

The MultiQuote endpoint provides a credit applicant with real time quotation on appropriate NewDay credit products. Hence, you can extend instant credit facility to your applicants.
The endpoint performs the following:  

1. You provide an applicant's details to the MultiQuote endpoint.  
2. The endpoint validates the applicant's information.  
3. It selects the specific suite of NewDay credit products that are applicable to your business, and responds with a quotation for each product. The MultiQuote API returns any of the following response:  
    * **Pre-approved**: The applicant is approved to apply for NewDay credit.
    * **Referred**: The applicant cannot be guaranteed of any credit facility. In this scenario, the applicant needs to provide further information for credit acceptance.
    * **Declined**: The application for availing NewDay credit is rejected.

> **Note** Credit quotation for each product mentions the Annual Percentage Rate (APR) and the maximum credit limit allowed to the applicant.

## Benefits

* **Instant credit decision**: The API provides credit quotation on each appropriate NewDay product and enables an applicant to instantly apply for credit.  
* **Straight forward decision**: The API responds with binary decisions — whether the applicant is accepted to apply for credit, needs to provide with additional information, or is rejected.
* **APR and credit limit**: The API response mentions the APR of a NewDay product and the maximum credit limit allowed to the applicant.

>**Note** If you are procuring Open Banking consent from your applicants, NewDay will support you in your initiative with using Open Banking data. In fact, this process enhances an applicant's chance of being approved for NewDay credit.

## MultiQuote API in the Acquisition Workflow

The following illustration explains how the MultiQuote API interfaces with your business to provide credit to your user:

![MultiQuote API Workflow](./MultiQuote%20API%20Workflow.png)
