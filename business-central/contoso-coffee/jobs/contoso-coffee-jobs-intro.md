---
title: Introduction to Contoso Coffee Project Management
description: This article introduces you to the Consoso Coffee demonstration data for jobs and project management.
author: andreipanko
ms.author: andreipa
ms.topic: how-to
ms.date: 05/31/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Introduction to Contoso Coffee Jobs and Project Management

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the Jobs and Project Management capabilities in Business Central.

This app provides several elements that are used for the main walkthroughs:

- Resources with assigned Skills and Zones
- Items configured to create Service Items

> [!IMPORTANT]
> Before you run any of the scenarios for Contoso Coffee, post any item journal lines with opening balances. For more requirements, see the [Set up Contoso Coffee data](#set-up-contoso-coffee-jobs-and-project-management-data) section.
>
> 
## Set up Contoso Coffee Jobs and Project Management data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Once the relevant apps are installed, go to the [Contoso Coffee Jobs Demo Data](https://businesscentral.dynamics.com/?page=4767) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], and change the default settings to suit your needs. The following tables describes the settings:  

|Field  |Description  |
|---------|---------|
|**Starting Year** |Specifies the first year that you you want to use for the Contoso Coffee demonstration data. Depending on the company setup, the year is either a calendar year or a fiscal year.|
|**Customer No.**  |The customer to use for the scenarios in sales operations.|
|**Item 1 No.**  |The item to use for the contract scenarios.|
|**Item 2 No.**  |The item to use for the breakfix scenarios.|
|**Resource Local 1 No.**  |The resource to use for the contract scenarios.|
|**Resource Remote 1 No.**  |The resource to use for the breakfix scenarios.|
|**Customer Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Customer General Business Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Domestic - General Business Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Resale - Inventory Posting Group**    |Specifies a code for items that must be used for posting resale.|
|**Retail - General Product Posting Group**    |Specifies a code for items that must be used for posting retail.|
|**VAT Product Posting Group**    |Specifies a VAT product code for items for posting VAT if VAT is enabled..|
|**Price Factor**     |Specifies a factor to convert a price from USD/EUR to the local currency. *1* means that the price is the same amount in any currency. A higher number will be used to get the price in the local currency. |
|**Rounding Precision**  |Defines how calculated consumption quantities are rounded when entered on consumption journal lines. Quantities less than 0.5 will be rounded down. Quantities equal to or greater than 0.5 will be rounded up.|

Once you're ready, choose the **Create Demo Data** action. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios.  

## Related information
