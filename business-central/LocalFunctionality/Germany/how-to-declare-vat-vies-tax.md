---
title: How to Declare VAT-VIES Tax [DE]
description:  Learn to create the VAT-VIES report for submitting sales transaction details with other EU countries or regions.
author: brentholtorf  
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT-VIES tax, VAT-VIES declaration, sales transactions, VAT-VIES declaration report
ms.date: 04/24/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Declare VAT-VIES tax in the German version

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes the **EC Sales List** report, which you can use to submit information about sales transactions with other European Union (EU) countries/regions to the customs and tax authorities' list system. The report displays information in the same format that is used in the customs and tax authorities' declaration list.  

Depending on the volume of sales of goods or services to other EU countries/regions, you must submit monthly, bi-monthly, or quarterly declarations. If your company has sales of more than 100,000 euros per quarter, you must submit a monthly declaration. If your company has sales of less than 100,000 euros per quarter, you must submit a quarterly declaration. Learn more in [BZSt website](https://go.microsoft.com/fwlink/?LinkId=204368).  

The report is based on the VAT Entry table.  

## Declare VAT-VIES tax  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT-Vies Declaration Tax – DE**, and then choose the related link.  
1. On the **VAT-Vies Declaration Tax – DE** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Reporting Period**|Select the time period that the report applies to. This can be a month, a two-month period, a quarter, or the calendar year.|  
    |**Date of Signature**|Enter the date on which the VAT-VIES declaration is sent.|  
    |**Corrected Notification**|If selected, this field indicates that this is a corrected version of an already delivered VAT-VIES declaration.|  
    |**Show Amounts in Add. Reporting Currency**|If selected, the amounts of the report are in the additional reporting currency. Learn more in [Additional Reporting Currency](../../finance-how-setup-additional-currencies.md).|  
    |**Change to monthly reporting**|If selected, your company has sales of more than 100,000 euros per quarter and you must migrate from a quarterly report to a monthly report. **Important:**  Only select this field the first time that you submit a monthly report.|  
    |**Revoke monthly reporting**|If selected, you want to switch from monthly reporting to another reporting period.<br><br/> For example, if you previously submitted monthly declarations but the EU sales are less than 100,000 euros per quarter, select this field and then select one of the quarters in the **Reporting Period** field.|  

1. On the **VAT Entry** FastTab, select the appropriate filters.  

    > [!NOTE]  
    > In order to run this report, you must select the **Posting Date** as a filter, and enter the posting date value.  

## Related information

- [VAT Reporting](vat-reporting.md)  
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
