---
title: Create Electronic VAT Transactions Reports for Italy
description: Learn how to create a VAT Transactions Report in Business Central for Italy, suggest lines for a posting-date range, and review included entries.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT-inclusive transactions, create VAT transaction reports, VAT report, Italian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create electronic VAT transactions reports in the Italian version

Create a VAT Transactions Report from the VAT entries in a posting-date range. The entries must be marked for inclusion, and the suggested report lines must meet the applicable threshold.

## Create a VAT transactions report

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Reports**, and then choose the related link.
1. Choose the **New** action.
1. In **VAT Report Config. Code**, select **VAT Transactions Report**. In **VAT Report Type**, select **Standard**.
1. Enter the **Start Date** and **End Date** for the posting dates to include.
1. Choose the **Suggest Lines** action.
1. Review the lines. Clear **Incl. in Report** for any line that must be excluded. To review the underlying VAT entries, select the amount on the line.

The **Contract Payment Type** field on a report line has the following options:

|Value|Description|
|-------------------------------------|---------------------------------------|
|**Without Contract**|The VAT entries that resulted in this line aren't associated with a contract.|
|**Contract**|The VAT entries that resulted in this line are associated with a contract.|
|**Other**|An alternative classification that you can choose when it applies to the transaction. **Suggest Lines** doesn't assign this value automatically.|

> [!IMPORTANT]
> If the report already has lines, **Suggest Lines** asks whether to delete and replace them. Review the suggested lines again after you regenerate them.

The suggested transaction types depend on the VAT entry's sales or purchase type, residency, and amounts. Learn more in [Italian VAT](italian-vat.md).

Now that you have created the VAT report, you must submit it to the tax authorities. Learn more in [Export VAT Transactions Reports](how-to-export-vat-transactions-reports.md).  

## Related information

[Italian VAT](italian-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
