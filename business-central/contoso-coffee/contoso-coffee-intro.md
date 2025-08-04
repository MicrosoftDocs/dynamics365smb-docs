---
title: Introduction to Contoso Coffee Demo Data
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the capabilities in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.date: 09/20/2023
ms.topic: concept-article
ms.service: dynamics-365-business-central
ms.search.form: 5194,
ms.custom: bap-template

---

# Introduction to Contoso Coffee Demo Data

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for [!INCLUDE [prod_short](../includes/prod_short.md)] add demo data that you can use to learn how to use the capabilities in [!INCLUDE [prod_short](../includes/prod_short.md)].  

## Set up Contoso Coffee data

[!INCLUDE [contoso-coffee-app-install](../includes/contoso-coffee-app-install.md)]

When the apps are installed, on the **Contoso Demo Tool** page, use the **Configure** action to prepare the following modules. You can choose to install all available data, which includes set up and production data, or setup data only.

 - The **Common Module** to prepare general settings that [!INCLUDE [prod_short](../includes/prod_short.md)] requires. For example, things like number series. Note that **Common Module** contains supplementary data for the Warehouse, Manufacturing, Service scenarios only. It is not recommended to run it in isolation.

The following table describes the settings:  

|Field  |Description  |
|---------|---------|
|**Starting Year** |Specifies the first year that you want to use for the Contoso Coffee demonstration data. Depending on the company setup, the year is either a calendar year or a fiscal year.|
|**Country/Region Code**|Specifies a country/region code for domestic customers and vendors.|
|**Company Type**    |Specifies if the current company must report VAT or sales tax. |
|**Price Factor**     |Specifies a factor to convert a price from USD/EUR to the local currency. *1* means that the price is the same amount in any currency. A higher number will be used to get the price in the local currency. |
|**Rounding Precision**  |Specifies the Rounding Precision that you want to create the demo data with.|

 - The [Manufacturing Module](manufacturing/contoso-coffee-manufacturing-intro.md) to prepare for [manufacturing scenarios](manufacturing/contoso-coffee-manufacturing-intro.md#scenarios).
 - The [Warehousing Module](warehousing/contoso-coffee-warehousing-intro.md) to prepare for [warehousing scenarios](warehousing/contoso-coffee-warehousing-intro.md#scenarios).
 - The [Service Module](service/contoso-coffee-service-intro.md) to prepare for [Service scenarios](service/contoso-coffee-service-intro.md#scenarios).

After you configure the modules you want to try out, choose the **Generate** action to create demonstration data for them.

## Related information

[Manufacturing](../production-manage-manufacturing.md)  
[Warehousing](../warehouse-manage-warehouse.md)  
[Service](../service-service.md)
<!-- [Projects and Jobs](../projects-manage-projects.md) -->

