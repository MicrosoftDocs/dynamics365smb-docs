---
title: Advance Payments Setup  
description: This section describes how to set up the Czech Advance Payments Localization extension in Business Central.  
author: v-pejano

ms.service: dynamics365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 10/01/2021  
ms.reviewer: v-pejano  
ms.author: v-pejano  
---

# Advance Payments Setup

To work with Advance Payments functionality, you must configure number series, posting accounts, and report selections.

## Advance Letter Templates

**Advance Letter Templates** are the foundation of the Advance Payments setup. They group advances into categories and provide default settings used to generate advance invoices.

![Advance Letter Templates](Media/adv-payments-setup-templates.png)

To configure advance templates:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Advance Letter Templates**, and then select the related link.
2. Fill in the following fields:
    - **Code** – Unique code to identify the template, typically per sales or purchase. You can create as many templates as needed, at least one per area.
    - **Description** – Description of the template.
    - **Sales/Purchase** – Specifies whether the template is for sales or purchase.
    - **Advance Letter Document Nos.** – Number series for advance letters.
    - **Advance Letter Invoice Nos.** – Number series for advance VAT documents.
    - **Advance Letter Cr. Memo Nos.** – Number series for advance VAT credit memos.
    - **Advance Letter G/L Account** – G/L account used to track advance payments (advance balances).
    - **VAT Bus. Posting Group** – Default VAT Business Posting Group for the template. If empty, the group from the customer/vendor is used; otherwise, the template setting takes precedence.
    - **Automatic Post VAT Document** – Indicates whether the VAT on the advance should be automatically posted when the advance is applied in a final invoice. For **sales**, this also controls automatic posting of the VAT document for the advance payment. For **purchases**, the VAT document must always be posted manually. The value can be changed per document.
    - **Automatic Post Non-Deductible VAT** – Indicates whether non-deductible VAT should be automatically posted.
    - **Post VAT document for Reverse charge** – Indicates whether post VAT document for reverse charge.
3. After completing the setup, you can close the page.

## VAT Posting Setup for Advances

For every combination of **VAT posting groups** that requires posting of a VAT document for an advance invoice, you must fill in the relevant fields on the **VAT Posting Setup** page under the **Advance CZZ** FastTab.

![VAT Posting Setup](Media/adv-payments-setup-vat.png)

To set up VAT posting for advance payments:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then select the related link.
2. On the list, select the VAT posting group combination you want to configure and choose **Edit**.
3. On the **Advance Payment** FastTab, fill in the following fields:
    - **Sales Advance Letter Account** / **Purchase Advance Letter Account** – G/L account for the advance base amount.
    - **Sales Advance Letter VAT Account** / **Purchase Advance Letter VAT Account** – G/L account for the advance VAT amount.

    The **VAT Document** or **Credit Memo** will be posted on these two accounts.  
    The **Advance Letter Account** may or may not be the same as the **Advance Letter G/L Account** defined in the template. The **Advance Letter VAT Account** is used exclusively for VAT tracking.
4. After finishing the setup, close the page.

## Report Selections for Sales and Purchases

Reports related to advances (advance invoices, VAT documents, and credit memos) are defined in **Report Selection**.

### Report Selection for Purchases

To configure report selection for **Purchase Advance Invoices**:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selection - Purchase**, and select the related link.
2. In the list, select the usage **Invoice**, and set the **Report ID** to **31028 Purchase – Invoice with Advance**.
3. Close the page when done.

### Report Selection for Sales

To configure report selection for **Sales Advance Invoices**:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selection - Sales**, and select the related link.
2. In the list, select the usage **Invoice**, and set the **Report ID** to **31189 Sales Invoice**.
3. Close the page when done.

## VAT Statement Setup

When posting VAT entries from advances, the standard **Base** and **Amount** fields are used. Therefore, the **Amount Type** in the **VAT Statement** only needs to be set to the standard **Base** and **Amount** options.  
VAT entries from advances are automatically included in the VAT statement, and no separate lines are needed for them.

## See Also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
