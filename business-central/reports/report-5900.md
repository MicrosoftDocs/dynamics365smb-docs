---
title: Service Order (document report)
description: Generate a service order that you can send to your customer.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5900_Primary
ms.date: 11/2/2024
ms.service: dynamics-365-business-central
ms.custom:
  - ai-gen-docs-bap
ai-seo-date: 10/23/2024
ai.usage: ai-assisted
---

# Service Order (document report)

Use the **Service Order** report to produce a service order that you can send to your customer.

The report displays information such as:

- Customer name
- Service order numberD
- Description of the service order
- Service order status
- Order date and time
- Contract number
- Service item and service lines

You can include either all or only selected service orders in the report.

You can display amounts in two ways:

- Quantity: The report shows the line amount, the amount including VAT, and the totals based on the difference between the values in the **Quantity** and the **Quantity Consumed** field on the service order's service line.
- Quantity Invoiced: The amounts are based on the value in the **Quantity Invoiced** field on the service order's service line.

## Use cases

[!INCLUDE[report-5900-scenario](../includes/report-5900-scenario-include.md)]

<!-- 

Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with project management or finance for projects.

Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

Do not start lines with "Use the data to"

## Report name
Service Order

## Report description

### What the report does

### Use cases

Please include your data sources and URLs

-->

## Try the report

Try the report here: [Service Order](https://businesscentral.dynamics.com?report=5900)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Service management report overview](../service-reports.md)  
[Service management](../service-service.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]