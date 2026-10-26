---
title: Norwegian VAT Codes in Business Central
description: Learn how to set up VAT processing information in the Norwegian version of Business Central by using standard Norwegian VAT codes.
author: brentholtorf
ms.topic: article
ms.search.keywords: use VAT codes, using VAT codes, VAT code usage, restricting VAT codes, VAT processing information, VAT codes, Norwegian version
ms.search.form: 10602, 10697, 10698, 10604
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Norwegian VAT codes

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can use Norwegian VAT codes to set up VAT processing information. In Business Central 29, maintain the codes on **VAT Reporting Codes** and assign them through **VAT Number**. These replace the former **VAT Codes** page and **VAT Code** field.

The following table shows examples of legacy VAT codes, not the current electronic VAT reporting code list. For electronic VAT reporting, use the codes configured through [Norwegian VAT reporting](norwegian-vat-reporting.md).

|**Code**|**Description**|  
|--------------|-------------------------------------------|  
|**0**|Sale - No VAT|  
|**1**|Purchase - VAT|  
|**2**|Purchase - VAT and Inv. Tax|  
|**3**|Sale - VAT|  
|**4**|Purchase - VAT and 0% Inv. Tax|  
|**11**|Purchase - Full VAT|  
|**13**|Sale - Full VAT|  
|**14**|Purchase - Reverse Charge VAT|  

Typically, you enter the **VAT Bus. Posting Group** and **VAT Prod. Posting Group** fields when you specify the VAT handling process.  

To fill in the posting groups with one field, assign a code in **VAT Number** on **VAT Posting Setup**. Then select **VAT Number** on the journal or document line. Each nonblank VAT number must identify a unique VAT posting setup combination.

## Set up Norwegian VAT codes

Create the Norwegian VAT codes on **VAT Reporting Codes**. Then assign the codes in **VAT Number** on **VAT Posting Setup**. If the field isn't shown, add it through personalization. Learn more in [Use one VAT code in journals](how-to-use-one-vat-code-in-journals.md).

## Use Norwegian VAT codes

When you specify a VAT code, you can select the VAT posting setup information for this code. This information is used in journals or on document lines when you specify the VAT setup information. If you use the VAT code in these cases, the posting group fields are used with the information from the corresponding VAT posting setup information.  

Alternatively, you must specify both the **VAT Bus. Posting Group** and the **VAT Prod. Posting Group** fields when you select or change the VAT posting setup information on the journal line or the document line.  

### Example: Use VAT codes

The following illustrative example uses two VAT posting setup combinations for sales. The rate is an example, not guidance on current statutory rates.

One VAT posting setup scenario calculates 24 percent VAT for domestic customers:  

- VAT Bus. Posting Group: DOMESTIC  
- VAT Prod. Posting Group: NORMAL  
- VAT %: 24  
- VAT Number: 3

One VAT posting setup scenario calculates without VAT for international customers:  

- VAT Bus. Posting Group: EXPORT  
- VAT Prod. Posting Group: NORMAL  
- VAT %: 0  
- VAT Number: 0

Typically, when you specify the VAT setup information on a journal line, the **VAT Bus. Posting Group** field must be set to **DOMESTIC** and the **VAT Prod. Posting Group** field must be set to **NORMAL** in order to choose the domestic setup.  

For this example, select **3** in **VAT Number** for domestic sales and **0** for sales without VAT. This lets you choose the VAT posting setup information using one field. Both codes must be configured for sales.

### Example: Restrict the use of VAT codes

The standard Norwegian **VAT Code 3** is used for sales inclusive of VAT. Unless you restrict the use of this VAT code, it can be used for both sales and purchases in [!INCLUDE[prod_short](../../includes/prod_short.md)].  

On **VAT Reporting Codes**, set **Gen. Posting Type** to **Sale** for code **3**.

The general posting type is handled in two ways, depending on the value in the **Test Gen. Posting Type** field.  

|Option|Description|  
|-----------------------------------------|-------------------------------------------|  
|**Mandatory**|The general posting type is automatically set to **Sale** on journal lines. Before you post, [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies if the general posting type is specified, but there's no verification if the field is set to **Sale**.<br> **VAT Code 3** can be used for both sales and purchase documents.|  
|**Same**|The general posting type is automatically set to **Sale** on journal lines. Before you post, [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies if the general posting type is set to **Sale**.<br> **VAT Code 3** can be used for sales documents, but not on purchase documents.<br> This enables you to restrict the use of VAT codes to predefined general posting types.|  

## Related information

[Norwegian VAT Reporting](norwegian-vat-reporting.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
