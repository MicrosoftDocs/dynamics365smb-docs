---
title: Set up advance payments in the Czech version  
description: This article describes how to set up Advance Payments in the Czech version.  
author: v-pejano
ms.reviewer: v-pejano  
ms.author: v-pejano  
ms.service: dynamics-365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 09/25/2025  
ms.custom: bap-template
---

# Set up advance payments in the Czech version

To work with Advance Payments functionality, you must configure:

- Number series
- Posting accounts
- Report selections

## Advance letter templates

Advance letter templates are the foundation of the setup for Advance Payments. They group advances into categories and provide default settings used to generate advance invoices.

![Advance Letter Templates](Media/adv-payments-setup-templates.png)

To configure an advance letter template, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Advance Letter Templates**, and then select the related link.
2. Fill in the following fields:
    - **Code** – Unique code to identify the template, typically per sales or purchase. You can create as many templates as you need, but create at least one per area.
    - **Description** – Description of the template.
    - **Sales/Purchase** – Specifies whether the template is for sales or purchase.
    - **Advance Letter Document Nos.** – Number series for advance letters.
    - **Advance Letter Invoice Nos.** – Number series for advance VAT documents.
    - **Advance Letter Cr. Memo Nos.** – Number series for advance VAT credit memos.
    - **Advance Letter G/L Account** – G/L account used to track advance payments (advance balances).
    - **VAT Bus. Posting Group** – Default VAT business posting group for the template. If empty, the group from the customer or vendor is used. The setting in the template takes precedence.
    - **Automatic Post VAT Document** – Indicates whether to automatically post the VAT on the advance when the advance is applied in a final invoice. For **sales**, this setting also controls automatic posting of the VAT document for the advance payment. For **purchases**, the VAT document must always be posted manually. The value can be changed per document.
    - **Automatic Post Non-Deductible VAT** – Indicates whether to automatically post nondeductible VAT.
    - **Post VAT document for Reverse charge** – Indicates whether post VAT document for reverse charge.
3. After completing the setup, you can close the page.

## VAT posting setup for advances

For every combination of VAT posting groups that requires posting of a VAT document for an advance invoice, you must fill in the relevant fields on the **Advance Payments** FastTab on the **VAT Posting Setup** page.

![VAT Posting Setup](Media/adv-payments-setup-vat.png)

To set up VAT posting for advance payments, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then select the related link.
2. Select the VAT posting group combination you want to configure, and choose **Edit**.
3. On the **Advance Payment** FastTab, fill in the following fields:
    - **Sales Advance Letter Account** / **Purchase Advance Letter Account** – G/L account for the advance base amount.
    - **Sales Advance Letter VAT Account** / **Purchase Advance Letter VAT Account** – G/L account for the advance VAT amount.

    The **VAT Document** or **Credit Memo** post to these two accounts.  
    The **Advance Letter Account** might or might not be the same as the **Advance Letter G/L Account** defined in the template. The **Advance Letter VAT Account** is used exclusively for VAT tracking.
4. After finishing the setup, close the page.

## Report selections for sales and purchases

You define the reports related to advances (advance invoices, VAT documents, and credit memos) using a report selection.

### Report selection for purchases

To configure report selection for purchase advance invoices, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selection - Purchase**, and select the related link.
2. Select the usage **Invoice**, and set the **Report ID** to **31028 Purchase – Invoice with Advance**.
3. Close the page.

### Report selection for sales

To configure report selection for sales advance invoices, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selection - Sales**, and select the related link.
2. Select the usage **Invoice**, and set the **Report ID** to **31189 Sales Invoice**.
3. Close the page.

## VAT statement setup

When you post VAT entries from advances, the standard **Base** and **Amount** fields are used. Therefore, the **Amount Type** field on the **VAT Statement** page only needs to be set to the standard **Base** and **Amount** options. VAT entries from advances are automatically included in the VAT statement, and no separate lines are needed for them.

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
