---
title: Brexit Impact on Business Central [GB]
description: Learn about recommended steps you can take in Business Central to help manage the impact of the United Kingdom leaving the European Union.
author: sorenfriisalexandersen
ms.topic: conceptual
ms.reviewer: v-soumramani
ms.search.keywords: united kingdom, uk, brexit, eu, european union, great britain, northern ireland
ms.date: 02/21/2025
ms.author: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Brexit impact on Business Central

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

The departure of the United Kingdom (UK) from the European Union (EU) will impact many businesses operating inside and across UK borders. As of January 1, 2021, it's likely the impact on UK businesses will revolve around these areas:

* Importing goods from the EU
* Exporting goods to the EU
* Moving goods to or from Northern Ireland

If your business performs any of the above activities, you'll likely need to make some configuration changes in [!INCLUDE[prod_short](../../includes/prod_short.md)].

> [!NOTE]  
> Make sure to check with His Majesty's Revenue and Customs (HMRC) for the latest information and to investigate the impact that Brexit might have on your business: [https://www.gov.uk/transition](https://www.gov.uk/transition). Microsoft will continuously monitor legislation changes due to Brexit and assess potential product impact.

## Trade across borders and the use of economic operators registration and identification numbers

Businesses in the UK are now subject to more administrative burdens when exporting and importing goods across borders, and one of these areas is with Customs. Although [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't support Customs documents by default, we have added a new **EORI number** field to the **Company Information**, **Customer**, and **Vendor** pages. This field is added to the international version (W1) and is available in all versions for European countries. In the UK version, we have also added a **Supplementary VAT Reg. Number** field on the **Company Information** page for scenarios where you must provide more than one of VAT registration number. For example, this number is typically on invoices, depending on the countries/regions of the specific trade and on the movement of goods and services.

Engage your [!INCLUDE[prod_short](../../includes/prod_short.md)] reselling partner for assistance with adding the **EORI number** or **Supplementary VAT Reg. Number** to the relevant reports.  

> [!NOTE]  
> If you're using [!INCLUDE[prod_short](../../includes/prod_short.md)] on-premises, to use the **EORI number**, **Supplemental VAT Reg. No.** and **Location Code** fields you must install the January 2021 Cumulative Update.

## Trade involving Northern Ireland

If part of your business is in Northern Ireland and you trade across EU borders or other European countries/regions, or your business is in one of these countries/regions and trade with a company or move goods into Northern Ireland, make sure to do the following actions:

* Add your **EORI number** and/or **Supplemental VAT Registration number** (starting with "XI") on the **Company Information** page.
* Add Northern Ireland to the **Countries/Regions** list.
* Specify this region on the relevant trading partners, such as customers and vendors.
* Specify an **EORI number** for your trading partners, such as customers and vendors.
* Specify Northern Ireland on the **Locations** page as the region for any warehouse locations you have in Northern Ireland.  

## Intrastat changes

Northern Ireland will have a dual position in the EU in areas related to the Customs Union, Single Market, VAT regime, and in the UK’s equivalents for goods (only). Goods moved in or out of Northern Ireland to or from European countries/regions must be reported on Intrastat. To handle this requirement, use Intrastat journals in [!INCLUDE[prod_short](../../includes/prod_short.md)].

Because Intrastat reporting is no longer needed for regular export and import for the UK, you may need to filter or delete such item movements on the **Intrastat Journal** when lines are suggested in the journal. To make it easier, we have added a **Location Code** field on the **Intrastat Journal Lines** so you can filter lines based on their **Ship-from** or **Receive-to** location.

## VAT impact on moving goods in and out of Northern Ireland

If your business has a warehouse in Northern Ireland, goods moved to that location will be subject to VAT as of January 1, 2021. When those goods are sold, VAT can be reclaimed. This and other scenarios involving the VAT process changes aren't supported by standard features in [!INCLUDE[prod_short](../../includes/prod_short.md)]. Although you may be able to configure [!INCLUDE[prod_short](../../includes/prod_short.md)] for your business, we recommend that you engage your [!INCLUDE[prod_short](../../includes/prod_short.md)] reselling partner to help ensure that your configuration changes are compliant and optimal for the scenarios that are specific to your business. Your partner can also refer you to product add-ons that you might need.

## Frequently asked questions

1. **I’m using [!INCLUDE[prod_short](../../includes/prod_short.md)] online – where is my data stored?**

    The data for UK customers using [!INCLUDE[prod_short](../../includes/prod_short.md)] online is stored in data centers in the UK. If you create another [!INCLUDE[prod_short](../../includes/prod_short.md)] environment in the same Microsoft Entra tenant, and choose another country/region for this environment, the data is stored in data centers that serve that specific country/region. In most cases, those data centers are outside the UK, which helps ensure optimal data residency and performance.

2. **Does [!INCLUDE[prod_short](../../includes/prod_short.md)] support legislation in the United Kingdom?**

    In many cases, yes. As with all countries/regions for which Microsoft provides a localized version, we follow the impact of local and EU-wide legislation and evaluate how we can support our customers. The responsibility for compliance rests on the individual business in a country/region, but we provide tools and features that can help our customers meet regulatory requirements, within the confines of our product strategy. A good example of that is our feature for Making Tax Digital, which makes VAT reporting easier and fully digital. There are, however, cases where regulations may require other feature support. For example, if regulatory changes impact a vertical industry, such as construction, we expect that the Microsoft Independent Software Vendor (ISV) who provides a solution that extends [!INCLUDE[prod_short](../../includes/prod_short.md)] for that industry delivers the features needed to comply. However, the business who uses the solution is responsible for compliance.

## See also

[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
