---
title: Correct VAT Transactions Reports in the Italian Version [IT]
description: Learn how to create a corrective or cancellation VAT transaction report in Business Central for Italy and record the tax authority's response.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: correct VAT transaction report, VAT report correction, resubmit VAT transaction report, Italian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Correct VAT transactions reports in the Italian version

Create a corrective report to replace a previous submission, or a cancellation report to cancel it. The original report must have the status **Submitted**.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Reports**, and then choose the related link.  
1. Create a new report. Learn more in [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md).  
1. In the new report, change the **VAT Report Type** field to **Corrective** or **Cancellation**. In the **Original Report No.** field, select the report that you want to correct from the list of available reports. The **Start Date** and **End Date** fields are copied from the original report.  

    > [!NOTE]  
    > You can only select VAT reports that are marked as Submitted, as it's required that the original report has a **Tax Auth. Receipt No.**  
    >
    > A cancellation report doesn't contain any lines.
    >
    > The suggested lines are based on the VAT entries within the specified period and the current threshold setup. They aren't copied from the original report.

1. For a corrective report, choose **Suggest Lines** to get the relevant VAT entries for the period.
1. Review the transaction details. To exclude a line from being reported to the tax authority, on the line, clear the **Incl. in Report** checkbox.

1. Choose the **Export** action. The **Export VAT Transactions** batch job opens. Select the export options, and choose **OK** to save the file.

    > [!NOTE]  
    > When you choose **Export** for a report with the status Open, it's automatically validated and the status is changed to Released. At this point, you can reopen the report to make changes.  

1. Submit the file to the authority. Use the guidelines provided by the authority. Learn more at [Italian Revenue Agency](https://go.microsoft.com/fwlink/?LinkID=206524).  

   After you receive a response from the tax authorities, you must update the VAT report.  

1. On the **General** FastTab, enter both **Tax Auth. Receipt No.** and **Tax Auth. Document No.** from the response that you received from the tax authorities.
1. Choose the **Mark as Submitted** action to finalize the report. The **Status** field is updated to Submitted.  

## Related information

[Export VAT Transactions Reports](how-to-export-vat-transactions-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
