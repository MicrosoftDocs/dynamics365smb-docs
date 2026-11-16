---
title: Introduction to Contoso Coffee Demo Data
description: Use Contoso Coffee demo data to explore manufacturing, warehousing, service, projects, and Expense Agent scenarios in Dynamics 365 Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.date: 11/12/2026
ms.topic: concept-article
ms.service: dynamics-365-business-central
ms.search.form: 5194,
ms.custom: bap-template
ai-usage: ai-assisted

---

# Introduction to Contoso Coffee demo data

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for [!INCLUDE [prod_short](../includes/prod_short.md)] add demo data that you can use to learn how to use the capabilities in [!INCLUDE [prod_short](../includes/prod_short.md)].  

## Set up Contoso Coffee data

[!INCLUDE [contoso-coffee-app-install](../includes/contoso-coffee-app-install.md)]

When the apps are installed, on the **Contoso Demo Tool** page, select a module and use the **Configure** action to prepare it. The following modules provide data for the Contoso Coffee walkthroughs.

 - The **Common** module prepares shared settings, such as number series, for manufacturing, warehousing, service, and project scenarios. We recommend generating data for a scenario module rather than running this module on its own.

The following table describes the settings:  

|Field  |Description  |
|---------|---------|
|**Starting Year** |Specifies the starting year used to adjust dates in the demo data.|
|**Starting Date** |Specifies the reference date for Analytics demo data.|
|**Country/Region Code**|Specifies a country/region code for domestic customers and vendors.|
|**Company Type**    |Specifies if the current company must report VAT or sales tax. |
|**Price Factor** |Specifies a multiplier applied to demo prices and costs before rounding. *1* keeps the original amounts. Increase the factor to scale the amounts for your local currency.|
|**Rounding Precision** |Specifies the precision used to round demo prices and costs after applying the price factor.|
|**Language Name** |Shows the language used when demo data was first generated. This field is read-only.|

 - The [Manufacturing module](manufacturing/contoso-coffee-manufacturing-intro.md) prepares data for manufacturing scenarios.
 - The [Warehouse module](warehousing/contoso-coffee-warehousing-intro.md) prepares data for warehousing scenarios.
 - The [Service module](service/contoso-coffee-service-intro.md) prepares data for service scenarios.
 - The [Job module](jobs/contoso-coffee-jobs-intro.md) prepares data for project scenarios.

After you configure the modules you want to try out, select them and choose **Generate**. This action creates setup data, master data, transactions, and history. Required dependency modules are generated automatically. Use this action to prepare for the walkthroughs.

To create only setup data, choose **Generate Setup Data** instead.

## Set up Expense Agent demo data

The separate **Expense Agent Demo Data** app adds the **Expense Agent** module to **Contoso Demo Tool**. The app requires **Expense Agent (Preview)** and **Contoso Coffee Demo Dataset**. The available modules depend on the apps installed in your environment.

Use a separate demo company. Generating Expense Agent data changes the expense setup, including turning off **Enable Agent** and **Use Rules**. It doesn't activate the agent for live expense processing.

Select **Expense Agent** and choose **Configure** to open **Expense Agent Module Setup**. The page includes **Create entries in Job Queue**, which is selected by default.

Choose **Generate** to create expense setup, payment methods, posting groups, categories, rules, users, sample expenses, and posted expense reports. Required **Human Resources**, **Job**, and **Finance** dependency modules are generated automatically. The data also includes country/region-specific expense categories and rules.

Learn more in [Expense Agent overview](../expense-management/expense-agent-overview.md).

## Related information

[Manufacturing](../production-manage-manufacturing.md)  
[Warehousing](../warehouse-manage-warehouse.md)  
[Service](../service-service.md)  
[Projects](../projects-manage-projects.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

