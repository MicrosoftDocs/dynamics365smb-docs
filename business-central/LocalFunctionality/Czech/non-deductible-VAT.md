---
title: Non-deductible VAT 
description: Learn about the features for using non-deductible VAT in the Czech version, including the setup, posting principles, and reporting requirements.
author: v-pejano
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Non-Deductible VAT, Localization
ms.date: 09/30/2025
ms.reviewer: v-soumramani
ms.author: v-jiurxo
---

# Non-deductible VAT in the Czech version

This article describes how to work with non-deductible VAT in the Czech version.

## Non-deductible VAT

If the VAT payer uses the received taxable supplies within their economic activities, both for supplies eligible for tax deduction and for tax-exempt, they can deduct tax only in the shortened amount. You must shorten VAT on input by the calculated coefficient. Non-deductible VAT functionality lets you apply a shortening coefficient to accounting cases.

You can set the value of the coefficient for the whole company in one place. The value applies to all marked combinations in the VAT posting setup. In addition to the input tax shortening through the shortening coefficient, you can also set a 100% tax reduction in the VAT posting setup. For example, when you can't apply VAT on the input side, but the output side (for reverse charge transactions) must report VAT in full. The VAT reduction also applies to the VAT Statement and the VAT Control Reports, which include the entire amounts. After the end of the calendar year, based on the calculated settlement coefficient, you can recalculate all VAT entries from the period and post the difference between the originally applied amounts and the settlement coefficient.

### Examples of tasks

- Set non-deductible VAT at a reduced or full amount.
- Adjust input VAT postings, include non-deductible VAT in related accounts and the purchase price of items or assets.
- Adjust VAT Statements and VAT Control reports.
- Run reports for VAT reconciliation.
- Apply a settlement coefficient at the end of the calendar period.

## Enable non-deductible VAT features

You enable non-deductible VAT features on the **VAT Setup** page by turning on the **Enable Non-Deductible VAT** toggle. When you select the **Enable Non-Deductible VAT** checkbox, you activate the standard functionality for non-deductible VAT. To enable the Czech extension of this functionality, also select **Enable Non-Deductible VAT CZ**. The standard functionality of non-deductible VAT is automatically extended for Czech accounting and reporting. Other related fields for settings are activated.

> [!NOTE]
> When you turn on the **Enable Non-Deductible VAT** toggle, the fields related to non-deductible VAT are enabled and you can't turn them off.

## Basic principles of posting non-deductible VAT

When you use non-deductible VAT on input (partial shortening through a shortening coefficient, or full shortening without deduction), the value of the non-deductible VAT is added to the basic account.

If there's no account in the **Non-Deductible Purchase VAT account** field in the relevant VAT combination on the **VAT Posting Setup**, the amount of non-deductible VAT is added to the account used in the posting entry. Otherwise (that is, if you set any account), this
account is used to post the non-deductible part of the VAT amount.

The amount posts to the VAT accounts at a reduced value, or not at all. However, you should report the amounts should in the original amount according to the original VAT document in the VAT Statement or VAT Control reports. To distinguish between the amounts in the posting and the amounts in the reporting, the non-deductible VAT features extend the **VAT Entries** table with the following fields:

- **Base** - Standard field, shows the amount of the reduced base.
- **Amount** - Standard field, shows the amount of reduced VAT.
- **Non-deductible VAT base** - Shows the amount of the base that isn't applied in VAT.
- **Non-deductible amount of VAT** - Shows the amount of VAT that isn't applied in VAT.
- **Deductible VAT base** - Shows the amount of the VAT base that's increased by non-deductible VAT.
- **Non-Deductible VAT %** - Shows the value of the VAT coefficient applied to the entry.
- **Original VAT Base** - Shows the value of the VAT base on the original document.
- **Original VAT Amount** - Shows the amount of VAT on the original document.

You must ensure that the **VAT Return** shows the original amounts in the original unreduced range. To learn more, go to [VAT report setup](#vat-report-setup).

The **VAT Control** report should also show the original amounts. The function for retrieving the lines of the control report is adapted so that it uses the **Original VAT Base** and **Original VAT Amount** from the VAT entry. Reduced values aren't included in the control report.

At the end of the calendar period, the advance coefficient must be recalculated retrospectively (which [!INCLUDE [prod_short](../../includes/prod_short.md)] doesn't support, you need to proceed in your usual way). The value of the calculated settlement coefficient is entered in the **Non-Deductible VAT Setup** in the appropriate field. It also becomes the value of the advance coefficient for the next period. If the settlement coefficient differs from the advance coefficient, you must run the **VAT Coefficient Correction** batch job to recalculate the entries.

This batch job goes through all VAT entries in the specified period with combinations of VAT posting groups set as input VAT reduction. It compares the value of the applied reduction coefficient in the **Non-deductible VAT %** field with the value of the posting coefficient. It calculates the difference and posts it as a new VAT entry with an adjusted VAT base and amount. The difference in VAT posts to the **VAT Coefficient Correction Account** specified on the **VAT Posting Setup** page.

## Non-deductible VAT setup

To work with non-deductible VAT, there are a few things to set up, as described in the following sections.

### Set the range of use non-deductible VAT

Non-deductible VAT automatically applies when you post accounting cases with direct posting to financial accounts. You can also use it when you post item cost for projects or fixed assets.

On the **VAT Setup** page, turn on the following toggles:

- **Use for Item Cost**
- **Use for Fixed Asset Cost**
- **Use for Project Cost**

When enabled, the value of the non-deductible VAT is automatically added to the purchase price of items, and the cost of assets or projects.

### VAT product posting groups setup

To post accounting cases with non-deductible input VAT, you need to create a new **VAT Product Posting Groups**. If you post entries with input VAT reduction and cases where you don't apply input VAT at all, set up a separate VAT Product Posting Groups for these cases, for example, as follows:

![VAT Product Posting Groups](Media/VAT-Product-Posting-Groups.png "VAT Product Posting Groups")  

### VAT posting setup

You must set up a combination of VAT product posting group and VAT business posting group to define how to post non-deductible VAT:

In the **Allow Non-Deductible VAT** field for the selected combination, select whether to charge non-deductible VAT, as follows:

- **Do Not Allow** means a standard combination of VAT posting groups for which VAT applies in full.
- **Allow** applies the input VAT reduction coefficient according to the **Non-Deductible VAT Setup**.
- **Do Not Apply** is for when you don't apply VAT on input. On output, it's in the full original extent, that is, a 100% shortening coefficient.

![VAT Posting Setup](Media/VAT-Posting-Setup.png "VAT Posting Setup")  

For combinations of VAT posting groups marked with **Allow** in the **Allow Non-Deductible VAT** field, you must set the **VAT Coefficient Correction Account** to which the difference between the shortening advance and settlement coefficient posts at the end of the calendar period.

### Non-deductible VAT setup

You set the value of the VAT shortening coefficient on the **Non-Deductible VAT Setup** page. For the calendar accounting period, you must set the **Advance Coefficient**, and then at the end of the period add the value of the recalculated **Settlement Coefficient**.

Both coefficients are set as percentages of the nonapplied part of VAT. That is, if the calculated shortening coefficient is 7% and therefore only 7% of input VAT is claimed, the value of the advance coefficient (the value of non-deductible VAT) is 93.

Setting the settlement coefficient is also related to the **Source Code Setup** page. On this page, you need to set the **Source Code** used in the annual posting of the difference between the advance and settlement coefficient. Set the value in the **VAT Coef. Correction** field.

### VAT report setup

The VAT statement must be supplemented with the VAT posting group combinations. Because the VAT statement must be entered with the original values, you must change the settings on the rows in the **Amount Type** field to use the values **Full Base** or **Full Amount**.

![VAT Statement](Media/VAT-Statement.png "VAT Statement")  

## Posting of non-deductible VAT in documents

The following examples assume the previous setup of non-deductible VAT, the created combinations of VAT posting groups, and the setup of the advance coefficient for the selected accounting period.

### Example of using reduced VAT in a purchase invoice - normal VAT

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and choose the related link.
1. On the **Purchase Invoices** page, choose **New** to create a new purchase invoice.
1. Fill in the fields on the purchase invoice header. Select a number from the number series, select the vendor number, posting date, VAT date, external document number.
1. In the purchase invoice line, select the value G/L Account in the **Type** field, and in the **No.** field, select an expense account from the chart of accounts. For example, 518100.
1. In the **VAT Business Posting Group** and **VAT Prod. Posting Group** fields, select the combination that is set for the normal input VAT reduced by the reduction coefficient
1. In the **Quantity** field, enter **1**, and in the **Direct Unit Cost Excl. VAT** field, enter **1.000**.
1. Choose the **Preview Posting** action to review the G/L Entry. Account 518100 is debited with the basic cost price of 1000, plus another entry for the proportionate amount of unapplied VAT. A reduction coefficient reduces the VAT amount.
1. Display the VAT entry. The fields for base and amount show the amounts corresponding to the value of the reduced, deductible VAT. The fields **Original VAT Base** and **Original VAT Amount** show the values of the base and VAT amount according to the values in the original document. That is, without reduction. The **Non-Deductible VAT %** field shows the value of the advance VAT coefficient.

### Example of the use of reduced VAT in a purchase invoice - VAT in reverse charge

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and choose the related link.
1. On the **Purchase Invoices** page, choose **New** to create a new purchase invoice.
1. Fill in the fields on the purchase invoice header. Select a number from the number series, select the vendor number, posting date, VAT date, external document number.
1. On the purchase invoice line, select **G/L Account** in the **Type** field. In the **No.** field, select an expense account from the chart of accounts. For example, 518100.
1. In the **VAT Business Posting Group** and **VAT Prod. Posting Group** fields, select the combination that is set for VAT in reverse charge mode reduced by the input reduction coefficient.
1. In the **Quantity** field, enter **1**, and in the **Direct Unit Cost Excl. VAT** field, enter **1.000**.
1. Choose the **Preview Posting** action to review the G/L Entry. Account 518100 is debited with the basic cost price of 1000 plus another entry for the proportionate amount of unapplied VAT. A reduction coefficient reduces the amount of input VAT. The output VAT amount is charged in full.
1. Display the VAT entry. The fields for base and amount show the amounts corresponding to the value of the reduced, applied VAT. The **Original VAT base** and **Original VAT amount** fields show the values of the base and VAT amount according to the values in the original document. That is, without reduction. The **Non-Deductible VAT %** field shows the value of the advance VAT coefficient.

### Example of the use of nonapplied VAT in a purchase invoice - normal VAT

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
1. On the **Purchase Invoices** page, choose **New** to create a new purchase invoice.
1. Fill in the fields on the purchase invoice header. Select a number from the number series, select the vendor number, posting date, VAT date, external document number.
1. On the purchase invoice line, select **G/L Account** in the **Type** field. In the **No.** field, select an expense account from the chart of accounts. For example, 518100.
1. In the **VAT Business Posting Group** and **VAT Prod. Posting Group** fields, select the combination that is set for normal VAT not applied on input (100% reduction).
1. In the **Quantity** field, enter **1**, and in the **Direct Unit Cost Excl. VAT** field, enter **1.000**.
1. Choose the **Preview Posting** action to review the G/L Entry. Account 518100 is debited with the basic cost price of 1000 plus the full amount of the calculated VAT in another entry. No VAT is charged at all.
1. Display the VAT entry. The fields for base and amount show zero amounts. The **Original VAT Base** and **Original VAT Amount** fields show the VAT base and amount values according to the values in the original document. That is, without reduction.

### Example of the use of nonapplied VAT in a purchase invoice - VAT in reverse charge

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
1. On the **Purchase Invoices** page, choose **New** to create a new purchase invoice.
1. Fill in the fields on the purchase invoice header. Select a number from the number series, select the vendor number, posting date, VAT date, external document number.
1. On the purchase invoice line, select **G/L Account** in the **Type** field. In the **No.** field, select an expense account from the chart of accounts. For example, 518100.
1. In the **VAT Business Posting Group** and **VAT Prod. Posting Group** fields, select the combination that is set for VAT in reverse charge mode reduced at 100%. That is, not applied at input.
1. In the **Quantity** field, enter **1**, and in the **Direct Unit Cost Excl. VAT** field, enter **1.000**.
1. Choose the **Preview Posting** action to review the G/L Entry. Account 518100 is charged with the basic cost price of 1000 plus the full amount of the calculated VAT in the next entry. Input VAT isn't charged at all, and output VAT is charged in full.
1. Display the VAT Entry. The fields for base and amount show zero amounts. The **Original VAT Base** and **Original VAT Amount** fields show the VAT base and amount values according to the values in the original document. That is, without reduction.

## VAT reporting with non-deductible VAT

For **VAT Statements**, you must change the settings of the VAT report so that the full amounts in the original values are included for rows that contain combinations of VAT posting groups reduced or not fully applied at input.

The value of the shortening coefficient can then be set manually in the corresponding row of the VAT report where the value in the **Type** field is **Formula**. To recalculate the input VAT only for selected rows of the report, create separate summation rows for the parts that include both full and reduced or nonapplied transactions that have full, reduced, and nonapplied transactions.

![VAT Report with coefficient](Media/VAT-Statement-coef.png "VAT Report with coefficient")  

You must export the VAT return in its original range, and make the reduction only for the selected total series, or the reduction must be made only on the VAT Portal website.

The **VAT Control Report** must be submitted in the original document amounts, not in the amounts reduced or not applied. Therefore, the task for retrieving the lines of the control report uses the **Original VAT base and Original VAT amount** fields from the VAT entry. The amounts that were reduced don't enter the report.

## Non-deductible VAT control reports

The **Documentation for VAT** report (**Recording obligation**) contains columns with VAT values in original and reduced amounts. The total value of the **Amount (LM)** column is a check on the accounting. The total value of the **Original VAT Amount** column is a check on the VAT report in original amounts.

There's a separate report layout for the **VAT Documents List** report. The layout contains columns with VAT values in original and reduced amounts. The total value of the **Amount (LM)** column is a check on the accounting. The total value of the **Original VAT Amount** column is a check on the VAT report in original amounts.

## VAT settlement coefficient

After the end of the calendar year, the accounting unit using the VAT shortening coefficient recalculates the transactions for the previous year and calculates the final VAT settlement coefficient (outside of [!INCLUDE [prod_short](../../includes/prod_short.md)]).

The newly calculated coefficient should be entered in **Non-deductible VAT Setup** as the settlement coefficient of the closed period and at the same time as the advance coefficient for the new accounting period.

If the coefficients differ in the completed period, you can use the **VAT Coefficient Correction** batch job to recalculate the VAT entries and record the difference in the accounting.

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT coefficient Correction**, and choose the related link.
1. Set the **Starting VAT Date and Ending VAT Date** in the batch job (should be the same as the calendar year for which you're recalculating). The **Ending VAT Date** must be the end date from the **Non-deductible VAT Setup** for which the settlement coefficient is set.
1. Toggle the **Post** field to control the test mode of the job or the actual posting of entries.
1. The option in the **Use Dimensions** field controls how dimensions are used for new items. It posts either without dimensions, or with the dimensions from the account set as the **VAT Coefficient Correction Account** in **VAT Posting Setup**.
1. In the **Use Document No** field, you can enter the number with which the coefficient adjustment entries post. If you don't enter a document number, the original document number is used for posting.

   > [!NOTE]
   > We recommend that you don't set the document number.

1. In the **Use Posting Date** field, set the posting date to which the posting should be made. If you don't specify a posting date, the original posting date of the entry is used.

   > [!NOTE]
   > We recommend that you use the last date of the calendar period as the posting date.

1. In the **Use VAT Date** field, set the VAT date with which the posting should be made. If you don't enter a VAT date, it uses the original VAT date of the entry.

   > [!NOTE]
   > We recommend that you enter the last date of the calendar period as the VAT date.

1. On the **Filter:** **VAT Entry** tab, you can specify **VAT Posting Group** filters for use in a batch job. It isn't necessary to set the filters. The batch job automatically passes only VAT entries with VAT posting group combinations that are marked in the **Allow non-deductible VAT** field with the value **Allow**.
1. The batch job goes through all (or filtered) VAT posting group combinations with an **Allow** value in the **Allow Non-Deductible VAT** field. It finds the value in the **Non-Deductible VAT %** field in the VAT entry posted and compares it to the settlement coefficient. If it finds a difference in the coefficient, it calculates the difference in the VAT amount, creates a new VAT entry, and posts the difference to the accounting records. All newly posted entries and VAT entries have a separate **Source Code** for subsequent filtering options.

## Related information

[Core Localization pack for Czech](ui-extensions-core-localization-pack-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[VAT Control Report](vat-control-report.md)  
[VAT Date](how-to-setup-vat-date.md)  
[Finance](../../finance.md)  
