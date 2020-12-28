---
title: Brexit impact on Business Central - United Kingdom leaving the European Union
description: Learn about recommended steps you can take in Business Central to help manage Brexit and impact after United Kingdom is leaving the European Union.
author: sorenfriisalexandersen
ms.service: dynamics365-business-central
ms.topic: article
ms.reviewer: edupont
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: united kingdom, uk, brexit, eu, european union, great britain, northern ireland
ms.date: 01/01/2021
ms.author: soalex

---
# Managing your business in the United Kingdom after the country leaves the European Union (Brexit)

The departure of the United Kingdom (UK) from the European Union (EU) will impact many businesses operating inside and across UK borders. As of January 1st, 2021, it is likely the impact on UK businesses will revolve around these areas:

* Importing goods from the EU
* Exporting goods to the EU
* Moving goods to or from Northern Ireland

If your business performs any of the above activities, you will likely need to make some configuration changes in [!INCLUDE[prod_short](../../includes/prod_short.md)].

> [!NOTE]  
>  Make sure to check with Her Majesty's Revenue and Customs (HMRC) for the latest information and to investigate the impact that Brexit might have on your business: [https://www.gov.uk/transition](https://www.gov.uk/transition). Microsoft is doing the same and will continuously monitor legislation changes for potential product impact.   


## Trade across borders and the use of Economic Operators Registration and Identification numbers 
Businesses in the UK are now subject to more administrative burdens when exporting and importing goods across borders, and one of these areas is with Customs. Although [!INCLUDE[prod_short](../../includes/prod_short.md)] does not support Customs documents by default, we have added a new **EORI number** field to the **Company Information** page. This is added to the international version (W1) and is available in all versions for European countries. In the UK version we have also added a **Supplementary VAT Reg. Number** field on the **Company Information** page to handle scenarios where you must express more than one of these numbers. For example, this is typically on invoices, depending on the countries/regions of the specific trade and on the movement of goods and services.

Please engage your [!INCLUDE[prod_short](../../includes/prod_short.md)] reselling partner for assistance with adding the **EORI number** or **Supplementary VAT Reg. Number** to the relevant reports.  

## Trade involving Northern Ireland
If part of your business is in Northern Ireland and you trade across EU borders or other European countries, or your business is in one of these countries and trade with a company or move goods into Northern Ireland, make sure to do the following:

* Add your **EORI number** and/or **Supplemental VAT Registration number** (starting with "XI") on **Company Information**.
* Add Northern Ireland to the **Countries/Regions** list.
* Specify this region on the relevant trading partners, such as customers and vendors.
* Specify **EORI number** on trading partners, such as customers and vendors.
* Specify this region for any warehouse locations you have in Northern Ireland on the **Locations** page.  

##  Intrastat changes
Northern Ireland will have a dual position in the EU in areas related to the Customs Union, Single Market and VAT regime, as well as in the UK’s equivalents for goods (only). This means that goods moved in or out of Northern Ireland to or from European countries must be reported on Intrastat. To handle this, you can use the Intrastat Journal in [!INCLUDE[prod_short](../../includes/prod_short.md)]. 

Because Intrastat reporting is no longer needed for regular export/import for UK, it may be needed to filter or delete such item movements on the **Intrastat Journal** when lines are suggested in the journal. To make this easier, we have added **Location Code** on the **Intrastat Journal Lines**. This enables you to easily filter lines based on their **Ship-from** or **Receive-to** location and exclude those that are not relevant. 

## VAT impact of goods moved in and out of Northern Ireland
If your business has a warehouse in Northern Ireland, goods moved to that location will be subject of VAT as of January 1st, 2021. When goods are then sold, VAT can be reclaimed. This, and other scenarios involving the VAT process changes, are not scenarios supported by dedicated features in [!INCLUDE[prod_short](../../includes/prod_short.md)]. While you may be able to configure [!INCLUDE[prod_short](../../includes/prod_short.md)] to handle the situation relevant for your business, we recommend that you engage your [!INCLUDE[prod_short](../../includes/prod_short.md)] reselling partner to help ensure that your configuration changes are correct and optimal for the scenarios that are specific to your business. Your partner can also refer you to product add-ons that you might need. 

## Frequently asked questions

1. **I’m using Business Central online – where is my data stored?**

    The data for UK customers using [!INCLUDE[prod_short](../../includes/prod_short.md)] online is stored in data centers in the UK. If you create another [!INCLUDE[prod_short](../../includes/prod_short.md)] environment in the same Azure AD tenant, and choose another country for this environment, the data will be stored in data centers that serve that specific country. In most cases, those data centers are outside the UK. This is to ensure optimal data residency and performance.

2. **Does Business Central support legislation in the United Kingdom?**

    In many cases, yes. As with all countries for which Microsoft provides a localized version, we follow the impact of local and EU-wide legislation and evaluate how we can support our customers. The responsibility for compliance rests on the individual business in a country, but we provide tools and features that can help our customers meet regulatory requirements, within the confines of our product strategy. A good example of that is our feature for Making Tax Digital, which makes VAT reporting easier and fully digital. There are, however, cases where regulations may require additional feature support. For example, when regulations impact a specific vertical industry, such as construction, we expect the solution that extends [!INCLUDE[prod_short](../../includes/prod_short.md)] for that industry by a Microsoft Independent Software Vendor (ISV) to provide the necessary features for the regulatory requirements specific to that vertical. Again, the responsibility for compliance rests with the individual business deploying the solution.

### Questions?

Contact the [!INCLUDE[prod_short](../../includes/prod_short.md)] localization team if you have any questions regarding localization of [!INCLUDE[prod_short](../../includes/prod_short.md)] at d365bcloc@microsoft.com.

## See Also

[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
