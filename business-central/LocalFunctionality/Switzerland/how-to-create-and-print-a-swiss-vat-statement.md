---
title: Create and Print a Swiss VAT Statement in the Swiss Version [CH]
description: Create a Swiss VAT statement template from VAT posting setup, review the statement lines, and print a report for the selected reporting period.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Swiss VAT statement, VAT posting setup, Swiss version
ms.search.form: 11023, 11024
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create and print a Swiss VAT statement in the Swiss version

Based on the information that you specified on the **VAT Posting Setup** page, [!INCLUDE[prod_short](../../includes/prod_short.md)] can automatically create a new VAT Statement Setup for realized VAT reporting. Before proceeding with the procedures in this article, make sure that you have set up VAT posting setup with values specified for the sales and purchase cipher fields.  

>[!NOTE]
> From January 2024 onward, the Cronus company's VAT Statement has been refreshed to include new Ciphers 303 and 383.  

## Set up a Swiss VAT statement template  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Update VAT Statement Template**, and then choose the related link.  
1. Select a template in the **VAT Statement Template Name** field.
1. Choose the **OK** button. Choose the **Yes** button to confirm that you want to create a new template.  
1. Check the resulting VAT Statement and adjust as needed.  

   The VAT Statement page contains the **VAT Statement Cipher** field, which indicates in which cipher of the report the result will be printed. This field is automatically populated by the batch job based on the information on the **VAT Posting Setup** page. The field can be edited if needed.  

## Print the Swiss VAT statement  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Swiss VAT Statement**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Enter the date that you want the time interval for VAT statement lines that appear in the report to start.|  
    |**Ending Date**|Enter the date that you want the time interval for VAT statement lines that appear in the report to end.|  
    |**Closed with VAT Register No.**|Select the VAT Register that contains the posting source of the VAT adjusting entries. This option evaluates accounting periods that have already been settled. When you choose this option, you don't specify options in the following **Include VAT Entries** fields.|  
    |**Include VAT Entries**|Select one of the available options.|  
    |**Normal Rate %**|Enter the standard VAT rate that applies to the time period.|  
    |**Reduced Rate %**|Enter the reduced VAT tax for certain goods and services.|  
    |**Hotel Rate %**|Enter the VAT rate for accommodation that applies to the time period.|  
    |**Normal (Earlier Rate) %**|Enter the standard VAT rate that applied before the current rate period.|
    |**Reduced (Earlier Rate) %**|Enter the reduced VAT rate that applied before the current rate period.|
    |**Hotel (Earlier Rate) %**|Enter the accommodation VAT rate that applied before the current rate period.|
    |**Ending Date of Earlier VAT Rates**|Specify the last date for earlier VAT rates. The date is adjusted to the end of the selected calendar year.|
    |**Show Amounts in Add. Reporting Currency**|Select to show amounts in an additional reporting currency.|  

1. Choose **Print** to print the statement, or **Preview** to review it.

## Related information

[Swiss Value Added Tax](swiss-value-added-tax.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
