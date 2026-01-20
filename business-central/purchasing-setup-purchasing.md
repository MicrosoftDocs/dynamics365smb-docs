---
title: Overview of tasks to set up purchasing
description: Describes the tasks to define your company's procurement policies and set up your purchasing processes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: overview
ms.devlang: al
ms.search.keywords: procurement, supply, vendor order
ms.search.form: 175, 176, 177, 178, 456, 460, 5727, 5729
ms.date: 10/03/2025
ms.service: dynamics-365-business-central
---

# Setting up purchasing

Before you can manage purchase processes, you must configure the rules and values that define the company's purchase policies.

You must define the general setup on the **Purchases & Payables Setup** page, which is typically done once during the initial implementation. Learn more in the [Purchases, and payables setup](#purchases-and-payables-setup) section.

A separate series of tasks related to registering new vendors is to record any special price or discount agreements you have with each vendor.

Finance-related purchase setup, such as payment methods and currencies, are covered in the finance setup section. Learn more in [Setting Up Finance](finance-setup-finance.md). Similarly, inventory-related purchase setup, such as units of measure and item tracking codes, can be found in the [Inventory Setup section](inventory-setup-inventory.md).

## Purchases and payables setup

Before working with purchases and payables, specify on the **Purchases & Payables Setup** page how purchase values are posted and the number series used for vendors and purchase documents.

### General settings

On the **General** FastTab, you specify options such as how you want to calculate and post discounts and whether you want to round invoices. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

Some fields require special attention, such as the **Calc. Inv. Disc. per VAT/Tax ID** field, which specifies whether the invoice discount is calculated according to the tax identifier or the invoice total. Learn more at [Combine VAT posting groups in VAT posting setups](finance-setup-vat.md#combine-vat-posting-groups-in-vat-posting-setups).

Similarly, the **Appln. between Currencies** field can result in small rounding differences when applying entries in different currencies to one another. Learn more in [Enable Application of Ledger Entries in Different Currencies](finance-how-enable-application-ledger-entries-different-currencies.md).

Also, some fields change their behavior or depend on how other fields are set. For example, the **Check Prepmt. when Posting** feature is influenced by how the **Prepmt. Auto Update** field is set to check for pending prepayments.

Learn more about the [**Ext. Doc. No. Mandatory**](#external-document-number) and [**Exact Cost Reversing Mandatory**](#exact-cost-reversing) fields in sections later in this article.

### Number series settings

On the **Number Series** FastTab, you must specify unique identification codes to use for vendors, invoices, and other purchase documents. Numbering is important not only for internal processes, but might also need to follow local regulations. So it might be worth considering setting up all series in the **No. Series** page beforehand instead of creating new ones from the **Purchases & Payables Setup**. Learn more in [Create Number Series](ui-create-number-series.md).

## External document number

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## Exact cost reversing

The **Exact Cost Reversing Mandatory** function helps ensure returned goods are valued at the same cost as when they were originally drawn from inventory, using a fixed application instead of following an average or first-in, first-out (FIFO) costing method. Learn more in the [Design Details: Fixed Application](design-details-item-application.md#fixed-application) section. If an extra cost is later added to the original purchase, the program updates the value of the respective purchase return.

With the feature enabled, a return transaction can only be posted by specifying the item ledger entry number in the **Appl.-to Item Entry** field on the purchase return order line. By default, the field isn't displayed on the **Lines** FastTab. Learn more in the [Personalize Your Workspace](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode) section for information on how to add fields to pages.

[!INCLUDE[local-functionality](includes/local-functionality.md)]

## More purchasing setups

| To | Go to |
|--|--|
| Create a vendor card for each vendor you purchase from. | [Register New Vendors](purchasing-how-register-new-vendors.md) |
| Prioritize vendors. | [Prioritize Vendors](purchasing-how-prioritize-vendors.md) |
| Enter bank account information&mdash;including International Bank Account Number (IBAN) and SWIFT Codes&mdash;to your vendor's card. | [Set Up Vendor Bank Accounts](purchasing-how-set-up-vendors-bank-accounts.md) |
| Set up purchasers, assign them vendors, and codes to track statistics. | [Set Up Purchasers](purchasing-how-setup-purchasers.md) |
| Enter the different discounts and special prices vendors grant you depending on item, quantities, and/or date. | [Record Purchase Price, Discount, and Payment Agreements](purchasing-how-record-purchase-price-discount-payment-agreements.md) |
| Define what you pay for the items and services purchased by your company. | [Set Up Prices and Discounts](across-prices-and-discounts.md) |
| Create standard lines to be inserted on recurring purchase documents. | [Set Up Recurring Purchase Lines](purchasing-how-work-recurring-purchase-lines.md) |
| Create sequences of tasks to connect processes performed by different users, such as requesting and approving purchase orders. | [Set Up Purchase Approval Workflows](across-set-up-workflows.md) |
| Manage business interactions with your vendors, import received invoice documents, and register new suppliers using the Outlook email client. | [Set Up the Business Central Add-in for Outlook](admin-outlook.md) |
| Review expense receipts, convert paper and electronic documents to journal lines, and digitalize paper invoices from vendors. | [Set Up Incoming Documents](across-how-setup-income-documents.md) |
| Specify default reports to be used for different document types. | [Report Selection in Business Central](across-report-selections.md) |
| Specify whether users are allowed to post purchase invoices, and whether they must post them together with a shipment. | [Define an invoice posting policy for users](admin-setup-invoice-posting-policy.md) |

## Related information

[Purchasing](purchasing-manage-purchasing.md)  
[Set Up Overview](setup.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
