---
title: Managing Brexit in Business Central
description: Learn about recommended steps you can take in Business Central to help manage Brexit.
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
# Managing your business in United Kingdom after leaving the European Union

The departure of the United Kingdom (UK) from the European Union (EU), will impact many businesses operating inside and across UK borders. As per January 1st 2021 it is likely that impact on UK businesses will revolve around these areas:
* Importing goods from the EU
* Exporting goods to the EU
* Moving goods to or from Northern Ireland

If your business perform any of the above activities it is likely you need to do configuration changes in [!INCLUDE[prodshort](../../includes/prodshort.md)].

> [!NOTE]  
>  Make sure to check the latest information from Her Majesty's Revenue and Customs (HMRC) for the latest information and Brexit impact for your business: [https://www.gov.uk/transition](https://www.gov.uk/transition).  

## Trade across borders and use of Economic Operators Registration and Identification numbers. 
Having left the European Union, businesses in United Kingdom are now subject to more administrative burdens when trading across borders, export and importing goods. One of these areas are with Customs when goods are crossing the borders. While [!INCLUDE[prodshort](../../includes/prodshort.md)] does not support Customs documents per default, we have added a new EORI number field to Company Information. This is added to the international version (W1) and visible in all country versions in Europe. In the UK version of [!INCLUDE[prodshort](../../includes/prodshort.md)] we have also added a **Supplementary VAT Reg. Number** field on **Company Information** to handle scenarios where you must express multiple such identifiers. This is typically on invoices, depending on the countries/regions of the specific trade and depends on the movements of goods and services.

Please engage your [!INCLUDE[prodshort](../../includes/prodshort.md)] reselling partner for assistance with adding the **EORI number** or **Supplementary VAT Reg. Number** to relevant reports in [!INCLUDE[prodshort](../../includes/prodshort.md)].  

## Trade involving Northern Ireland
If part of your business is in Northern Ireland and you trade across EU borders or other European countriers, or your business are in one of these countries and trade with a company or move goods into Northern Ireland, you should make sure to:
* Add Northern Ireland to the **Countries/Regions** list
* Specify this region on relevant trading partners, customers and vendors.
* Specify this region on the details for warehouse locations you have in Northern Ireland. This can be done through the **Locations** page.  

##  Intrastat changes
Northern Ireland will have a dual position in the EU in areas related to the Customs Union, Single Market and VAT regime as well as in the UK’s equivalents for goods (only). This means that goods moved into or out of Northern Ireland must still be reported on Intrastat. To handle this, you can still use the Intrastat Journal in [!INCLUDE[prodshort](../../includes/prodshort.md)]. 

Since Intrastat reporting is no longer needed for regular export/import for UK, it may be needed to filter out/delete such item movements on the **Intrastat Journal** when lines are suggested in the journal. To make this easier, we have added **Location Code** on the **Intrastat Journal Lines**. This enables you to easily filter lines based on their **Ship-from** or **Receive-to** location and exclude those not relevant for Northern Ireland. 

## VAT impact of goods moved to and from Northern Ireland
If your business has a warehouse in Northern Ireland, goods moved to that location will be subject of VAT as per January 1st 2021. When goods are then sold, VAT can be reclaimed. This, and other scenarios involving the VAT process changes, are not scenarios supported by dedicated features in [!INCLUDE[prodshort](../../includes/prodshort.md)]. While you may be able to configure [!INCLUDE[prodshort](../../includes/prodshort.md)] to handle the situation relevant for your business, we recommend to engage your [!INCLUDE[prodshort](../../includes/prodshort.md)] reselling partner for assistance to make sure you are doing the correct configuration changes to handle the scenarios specific to your business. Your partner can also refer you to potential product addons needed. 

## Frequently asked questions

1. **I’m using the online version of Business Central – where is my data stored?**

    The data for UK customers of [!INCLUDE[prodshort](../../includes/prodshort.md)] online is stored in data centers in the United Kingdom. If you create another [!INCLUDE[prodshort](../../includes/prodshort.md)] environment in the same Azure AD tenant, and choose another country for this environment, the data will be stored in data centers that serve that specific country. In most cases, those data centers are outside the United Kingdom. This is to ensure optimal data residency and performance.

2. **Does Business Central support legislation in the United Kingdom?**

    In many cases, yes. As with all countries for which Microsoft provides a localized version, we follow the impact of local and EU-wide legislation and evaluate how we can support our customers. The responsibility for compliance rests on the individual business in a country, but we provide tools and features that can help our customers meet regulatory requirements, within the confines of our product strategy. A good example of that is our feature for Making Tax Digital, which makes VAT reporting easier and fully digital. There are, however, cases where regulations may require additional feature support. For example, when regulations impact a specific vertical industry, such as construction, we expect the solution that extends [!INCLUDE[prodshort](../../includes/prodshort.md)] for that industry by a Microsoft Independent Software Vendor (ISV) to provide the necessary features for the regulatory requirements specific to that vertical. Again, the responsibility for compliance rests with the individual business deploying the solution.

### Questions?

Contact the [!INCLUDE[prodshort](../../includes/prodshort.md)] localization team if you have any questions regarding localization of [!INCLUDE[prodshort](../../includes/prodshort.md)] at d365bcloc@microsoft.com.

## See Also

[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
