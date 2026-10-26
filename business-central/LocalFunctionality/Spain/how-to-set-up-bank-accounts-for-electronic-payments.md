---
title: Set Up Bank Accounts for Electronic Payments in Spain
description: Learn how to configure bank and vendor bank accounts for electronic payments in Business Central for Spain, including export and remittance details.
author: brentholtorf   
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic payment, bank accounts, vendor bank accounts, Spanish version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up bank accounts for electronic payments in the Spanish version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can set up bank accounts to make electronic payments.  

## Set up bank accounts for electronic payments  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Bank Account Card**, and then choose the related link.  
1. On the **Transfer** FastTab, make sure that the **CCC Bank No.**, **CCC Bank Branch No.**, **CCC Control Digits**, and **CCC Bank Account No.** fields are filled in correctly.  
1. On the **Transfer** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**E-Pay Export File Path**|Enter the full path of the electronic payment file, start with the drive letter and end with a backslash (\\). The file name isn't included here. You should use the directory where [!INCLUDE[prod_short](../../includes/prod_short.md)] is installed. For example: **C:\NAV\** would be a possible entry for this field. You can enter a maximum of 100 characters.|  
    |**Last E-Pay Export File Name**|Specify the name of the file with the .txt file name extension, without the path. Because the file name is incremented every time that an electronic payment file is exported, this file name should have digits in it. This creates a permanent record of every file that you have exported to the bank. For example, **DD000000.txt** could be a possible first entry for this field. You can enter a maximum of 50 characters.|  

1. On the **Posting** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Last Remittance Advice No.**|Specify a number series that differs from the check number series. This is needed so that the numbers don't conflict with each other. The remittance advice is printed on blank paper in a form that is easy to mail to the vendor.|  

## Set up vendor bank accounts for electronic payments  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendor Bank Account Card**, and then choose the related link.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Use For Electronic Payments**|Specify if this vendor bank account is used for electronic payments. For electronic payments, only one bank account can be selected for each vendor.|  

1. On the **Transfer** FastTab, make sure that the **CCC Bank No.**, **CCC Bank Branch No.**, **CCC Control Digits**, and **CCC Bank Account No.** fields are filled in correctly.  

## Related information

[Electronic Payments – AEB N34.1](electronic-payments-aeb-n341.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
