---
title: Import Swiss Post Codes in the Swiss Version [CH]
description: Learn how to import the latest Swiss post code file to update the Post Code table and define post codes for customers or vendors efficiently.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: post code file, define post codes, import post codes, Swiss version
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import Swiss post codes in the Swiss version

You can import the latest post code file and use it to update the **Post Code** table. The post code file can be downloaded from the [Swiss Post](https://go.microsoft.com/fwlink/?LinkId=150292) website. After importing the latest post code, you can define post codes for customers or vendors. Learn more in [Register New Vendors](../../purchasing-how-register-new-vendors.md).  

## Import post codes  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Post Codes**, and then choose the related link.  
1. Choose the **Import Post Codes** action.  
1. Select the semicolon-delimited CSV file, or a ZIP file containing it, in the upload dialog.
1. Confirm that you want to delete existing post codes in the range **1000** to **9999** before importing the replacement records.

   The import reads the post code, city, and county from the first three CSV columns. It imports post codes in the range **1000** to **9999**. For a ZIP file, it reads the first archive entry.

## Define post codes for customers

The following procedure describes how to define post codes for customers, but the same steps also apply to defining post codes for vendors.  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customers**, and then choose the related link.  
1. Select the customer for whom you want to define a post code, and then choose the **Edit** action.  
1. On the **Customer Card** page, on the **General** FastTab, in the **Post Code** field, select the post code for the customer's address.  

    > [!NOTE]  
    > When you select the post code, the **City** and **Country/Region Code** fields populate automatically with the information from the **Post Code** table. Learn more in [Register New Customers](../../sales-how-register-new-customers.md).  

1. Choose the **OK** button.  

## Related information

- [Swiss Purchase Documents and Sales Documents](swiss-purchase-documents-and-sales-documents.md)
- [Print an Inventory Picking List from a Sales Order](how-to-print-an-inventory-picking-list-from-a-sales-order.md)
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
