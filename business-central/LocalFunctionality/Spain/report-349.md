---
title: Report 349 [ES]
description: Learn how to use Business Central to prepare and submit Report 349, the periodic declaration of trade with other EU countries/regions required by Spanish tax authorities.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: report 349, delivery operation codes, item setup, Spanish version
ms.date: 05/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Report 349 in the Spanish version

You must submit a periodic report of trade with other EU countries/regions to the tax authorities. In Spain, this Report 349 is part of the EU intra-community VAT Information Exchange System (VIES).  

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the Report 349 declaration is based on VAT entries that are filtered by the EU country/region codes. You must create a 349 declaration and then submit the file to the [Spanish Tax Agency](https://go.microsoft.com/fwlink/?LinkId=238181) website or on CD-ROM.  

When you create a Report 349 declaration that includes credit memos, the entries display on the **Customer/Vendor Warnings 349** page so that you can include them as corrections to invoices. You must make the appropriate changes to the lines on the **Customer/Vendor Warnings 349** page before you can submit the declaration. Learn more in [Create Report 349](how-to-create-report-349.md).  

## Delivery operation codes

The **Report 349** declaration must specify separate operation codes for the delivery of goods to other EU countries/regions. You can set up separate VAT product posting groups for each type of export delivery. Then, when you apply a VAT posting group to an item that is sold, [!INCLUDE[prod_short](../../includes/prod_short.md)] stores the delivery operation code, and the transaction is included in the quarterly 349 declaration.  

Before you submit the 349 declaration, you must make sure that all VAT entries have the relevant delivery operation codes. The following table describes the delivery operation codes that are currently supported in [!INCLUDE[prod_short](../../includes/prod_short.md)].  

|Delivery operation code|Description|  
|-----------------------------|---------------------------------------|  
|**E**|Identifies transactions with items that were delivered to customers in another EU country/region and aren't included in either the M or the H delivery operation code.|  
|**M**|Identifies transactions with items that were delivered to customers in another EU country/region and which were previously imported into Spain as tax exempt according to the VAT law.|  
|**H**|Identifies transactions with items that were delivered to customers in another EU country/region and which were previously imported into Spain as tax exempt according to the VAT law, and which were conducted by an official tax representative.|  

To help you manage exports to other EU countries/regions in [!INCLUDE[prod_short](../../includes/prod_short.md)], you can create VAT product posting groups for each operation code. Then, when you apply a VAT posting group to an item that is sold, the Delivery Operation Code field in the **VAT Entry** table identifies the VAT transactions according to the operation code.  

### Delivery operation codes and item setup

You can set up a VAT product posting group for each delivery operation type and then assign the appropriate VAT product posting group to items in the Item Card page.  

If you have an inventory item that can be imported in different ways, for example if its tax exempt in some cases and not tax exempt in other cases, you can create separate item cards with the appropriate VAT product posting group.  

In the following example, you import chairs from another EU country/region, and you resell the chairs to customers in other countries/regions. One type of chair is exempt from VAT when you import it under certain circumstances, but otherwise it isn't exempt. As a result, you create two item cards for it:  

- One item card with a VAT product posting group with the **Delivery Operation Code** field set to **M**.  
- One item card with a VAT product posting group with the **Delivery Operation Code** field set to **E**.  

Then, when you create a sales order, you must make sure that you select the correct item in the sales lines.  

When you post the sales invoice, [!INCLUDE[prod_short](../../includes/prod_short.md)] saves the delivery operation code in the **VAT Entry** table, and then, when you create the Report 349 declaration, the VAT amount is included in the section for the appropriate delivery operation code.  

## Related information

[Create Report 349](how-to-create-report-349.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
