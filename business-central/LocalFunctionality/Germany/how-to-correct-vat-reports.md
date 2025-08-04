---
title: Correct VAT Reports [DE]
description: If you need to submit a corrective VAT report or delete an existing one, you must create a new VAT report. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: corrective VAT report, VAT report, VAT report deletion, VAT report correction, German version
ms.search.form: 26101
ms.date: 03/10/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Correct VAT reports in the German version

If you have to submit a corrective VAT report or delete a submitted VAT report, you must create a new VAT report. According to the legislation, a corrective report must be submitted within a month of the initial report.  

When you create a corrective report, the report contains two line types per corrected line. In one line type, **Cancellation**, the base value of the VAT is reported as a cancellation. All other information remains the same, and can't be edited. On a new line, **Correction type**, you can make corrections as needed to the VAT amount. The **Suggest Lines** action, however, suggests the correct amount based on the filters and posted documents. You can't correct or modify the **VAT Registration No.**, each period being corrected needs its own corrective report.  

The **Suggest Lines** action recalculates the values to report. The **Correct Lines** action is used to make manual changes. You can combine the effects of the two actions to correct your report.  

## Example corrections scenarios

1. If you post additional VAT entries after you submit the Standard report in the report period, choose **Suggest Lines** in the **Process** group to get the updated amounts.  

    > [!NOTE]  
    > If you manually changed the amount for a customer or vendor, this amount is overwritten when additional VAT entries are posted. Update the amount accordingly.  

1. If you want to change the amount of a report line that is submitted and no new VAT entries are posted, choose the  **Correct Lines** action. On the **VAT Report Lines** page, select the lines that you want to correct, and then choose the **OK** button.  

    For each entry, two lines are displayed: **Cancellation** and **Correction**. You can now change the amount on the **Correction line**.  

    > [!NOTE]  
    > The **Correct Lines** action doesn't suggest the amount based in VAT entries. If you have new VAT entries for the customer or vendor, instead use the **Suggest Lines** action.  

1. If you used the wrong filters, for example, the wrong VAT product posting group, choose the **Suggest Lines** action, and then set filters as needed.  

    **Suggest Lines** creates entries to account for the difference between the filters.  

    > [!NOTE]  
    > If the updated filters exclude a customer or vendor, [!INCLUDE[prod_short](../../includes/prod_short.md)] creates a Cancellation line for the previous reported amount and a Correction entry with amount 0.

## Correct a VAT report  

1. Create a new VAT report. Learn more in [Create VAT Reports](how-to-create-vat-reports.md).  
1. Fill in the fields in the **General** FastTab, and set the **VAT Report Type** field to **Corrective**.  
1. In the **Original Report No.** field, select the report that you want to correct. You can only select reports of type **Standard** that are marked as **Submitted**.  
1. Create your correction VAT report line entries.  

    Choose the **Suggest Lines** action. Set filters as needed.  

    On each line, you can drill down on the amounts to see which VAT entries make up the amount. Change the amount if needed. You can't edit, however, the **VAT Registration No.**.  

1. If the **Suggest Lines** action doesn't provide suggestions to correct the amounts that you intended, use the **Correct Lines** action to insert cancellation and correction lines for the customer or vendor.  
1. Continue with the VAT report creation process, and release the report.  

## Related information

[Set Up VAT Reports](how-to-set-up-vat-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
