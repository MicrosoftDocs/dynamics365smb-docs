---
title: Update VAT Transactions Data for Italy
description: Learn how to prepare and update VAT transaction data using the Update VAT Transaction Data report before creating your first VAT transaction report.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: first VAT transaction report, prepare VAT data, update VAT data, VAT transaction data report, VAT transaction report, create VAT transaction report, Italian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Update VAT transactions data

Before you create the first VAT transaction report, you should prepare the existing data by running the **Update VAT Transaction Data** report. You should also run this report if you make changes to the setup based on new requirements from the tax authorities.  

You can run the **Update VAT Transaction Data** report as a test before you change any data. When you verify that the filters meet your expectations and the requirements of the tax authorities, you should run the report again to make the appropriate changes to data.  

> [!CAUTION]  
> Before you run the **Update VAT Transaction Data** report, you should activate the change log on the **Change Log Setup** page. Also, you should enable logging for modifications to the **Include in VAT Transac. Report** field on the **VAT Entry** table.  

## Steps to update VAT transaction data  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Update VAT Transaction Data**, and then choose the related link.  
1. Optionally, on the **VAT Entry** FastTab, set the appropriate filters.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Compare Against Threshold**|Select to compare the absolute VAT base with **Threshold Amount Excl. VAT**. The report uses the threshold with the latest starting date on or before the entry's **Operation Occurred Date**.|
    |**Show List Only**|Select to list the matching entries without changing them. This option disables **Set Include in VAT Transaction Report**.|
    |**Set Include in VAT Transaction Report**|Choose **Set Fields** to select **Include in VAT Transac. Rep.** on matching entries, or **Clear Fields** to clear it. This option applies only when **Show List Only** is cleared.|

1. Select **Show List Only**, and choose **Preview** to review the matching entries.
1. To apply the changes, run the report again with the same filters. Clear **Show List Only**, choose **Set Fields** or **Clear Fields**, and run the report. Confirm the update when prompted.

> [!CAUTION]
> **Show List Only**, not the choice between **Print** and **Preview**, controls whether the report changes data. Keep **Show List Only** selected for a test run.

When you run the report, [!INCLUDE[prod_short](../../includes/prod_short.md)] processes VAT entries based on the filters that you set. The following rules are also applied:  

The report excludes entries with **Type** set to **Settlement**. An entry also needs an applicable threshold record, even when **Compare Against Threshold** is cleared.

## Related information

- [Set Up VAT](../../finance-setup-vat.md)  
- [Prepare for VAT Transactions Reports](how-to-prepare-for-vat-transactions-reports.md)
- [Italian VAT](italian-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
