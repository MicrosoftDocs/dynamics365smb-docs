---
title: Norwegian VAT Codes
description: Learn how to set up VAT processing information in the Norwegian version of Business Central by using standard Norwegian VAT codes.
author: brentholtorf
ms.topic: article
ms.search.keywords: use VAT codes, using VAT codes, VAT code usage, restricting VAT codes, VAT processing information, VAT codes, Norwegian version
ms.search.form: 10602, 10697, 10698, 10604
ms.date: 05/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Norwegian VAT Codes

In [!INCLUDE[prod_short](../../includes/prod_short.md)], VAT processing information can be easily set up using standard Norwegian VAT codes. The following table shows the standard Norwegian VAT codes.  

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

If you want to use only the **VAT Code** field when you specify the VAT handling process, you can assign a VAT code in the **VAT Posting Setup** table, and use this code instead of the posting group fields. The VAT code can be used as a shortcut in the **VAT Posting Setup** table and at the same time, you can use standard Norwegian VAT codes.  

## Set Up of Norwegian VAT Codes

You must create the Norwegian VAT codes on the **VAT Codes** page. Then assign the VAT codes in the **VAT Posting Setup** table, using the **VAT Code** field. Learn more in [Use One VAT Code in Journals](how-to-use-one-vat-code-in-journals.md).  

## Use of VAT Codes

When you specify a VAT code, you can select the VAT posting setup information for this code. This information is used in journals or on document lines when you specify the VAT setup information. If you use the VAT code in these cases, the posting group fields are used with the information from the corresponding VAT posting setup information.  

Alternatively, you must specify both the **VAT Bus. Posting Group** and the **VAT Prod. Posting Group** fields when you select or change the VAT posting setup information on the journal line or the document line.  

### Example: Using VAT Codes

There are two different VAT posting setup instances that can be used when you post a sales document.  

One VAT posting setup scenario calculates 24 percent VAT for domestic customers:  

- VAT Bus. Posting Group: DOMESTIC  
- VAT Prod. Posting Group: NORMAL  
- VAT %: 24  
- VAT Code: 3  

One VAT posting setup scenario calculates without VAT for international customers:  

- VAT Bus. Posting Group: EXPORT  
- VAT Prod. Posting Group: NORMAL  
- VAT %: 0  
- VAT Code: 1  

Typically, when you specify the VAT setup information on a journal line, the **VAT Bus. Posting Group** field must be set to **DOMESTIC** and the **VAT Prod. Posting Group** field must be set to **NORMAL** in order to choose the domestic setup.  

If you use standard Norwegian VAT codes, you could specify **VAT Code 3** for the domestic VAT posting setup information, and **VAT Code 1** for the international VAT posting setup information. This lets you choose between the VAT posting setup information using only one field and the familiar standard Norwegian VAT codes.  

### Example: Restricting the use of VAT codes

The standard Norwegian **VAT Code 3** is used for sales inclusive of VAT. Unless you restrict the use of this VAT code, it can be used for both sales and purchases in [!INCLUDE[prod_short](../../includes/prod_short.md)].  

You can define the **Gen. Posting Type** field as a sale in the **G/L Account (Analysis View)** table. This general posting type is used together with **VAT Code 3**.  

The general posting type is handled in two ways, depending on the value in the **Test Gen. Posting Type** field.  

|Option|Description|  
|-----------------------------------------|-------------------------------------------|  
|**Mandatory**|The general posting type is automatically set to **Sale** on journal lines. Before you post, [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies if the general posting type is specified, but there's no verification if the field is set to **Sale**.<br> **VAT Code 3** can be used for both sales and purchase documents.|  
|**Same**|The general posting type is automatically set to **Sale** on journal lines. Before you post, [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies if the general posting type is set to **Sale**.<br> **VAT Code 3** can be used for sales documents, but not on purchase documents.<br> This enables you to restrict the use of VAT codes to predefined general posting types.|  

## Related information

[Norwegian VAT Reporting](norwegian-vat-reporting.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
