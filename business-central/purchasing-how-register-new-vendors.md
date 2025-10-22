---
title: Register a new vendor
description: Learn how to fill in a vendor card to register a new vendor or supplier, and how to save vendor cards as templates.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: supplier
ms.search.form: 26, 27, 34, 461, 786, 1379, 1385, 1386, 1628
ms.date: 06/10/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Register new vendors

Vendors provide the products you sell. Each vendor you purchase from must be registered with a vendor card.

Before you register new vendors, you must set up various purchase codes to select from when you fill in vendor cards. After all the required master data is created, you can add unique characteristics for a vendor, such as prioritize the vendor for payment purposes or list items that the vendor and other vendors supply. Another group of setup tasks for vendors is to record your agreements concerning discounts, prices, and payment methods. Learn more at [Setting Up Purchasing](purchasing-setup-purchasing.md).

Vendor cards hold the information required to buy products from each vendor. Learn more at [Record Purchases](purchasing-how-record-purchases.md) and [Register New Items](inventory-how-register-new-items.md).
<br /><br />  

> [!Video https://learn-video.azurefd.net/vod/player?id=7188b662-bc49-45ef-8152-82898076b235]

## Adding new vendors

You can add new vendors manually, by filling out the **Vendor Card** page, or you can use templates that contain predefined information. For example, you can create templates for different types of vendor profiles. Using templates saves time when adding new vendors, and helps ensure the information is correct each time.

> [!NOTE]  
> If vendor templates exist for different vendor types, when you create a new vendor you can select the appropriate template. If only one vendor template exists, new vendors always use that template.

After you create a template, you can use the **Apply Template** action to apply it to one or more selected vendors. To create a template, fill in the information you want to reuse on the **Vendor Card** page, then save it as a template. Learn more in the [To save the Vendor Card Page as a template](purchasing-how-register-new-vendors.md#to-save-the-vendor-card-as-a-template) section.

> [!TIP]
> It can be helpful to personalize the **Vendor Template** page when you create a template. For example, if you want to add a field that isn't already displayed on the page. Learn more at [Personalize your workspace](/dynamics365/business-central/ui-personalization-user#start-personalizing-by-using-the-personalization-mode).

You can also create a vendor from a contact. Learn more at [Creating a customer, vendor, employee, or bank account from a contact](marketing-create-contact-companies.md#create-a-customer-vendor-employee-or-bank-account-from-a-contact).

Remit-to addresses are used when you print checks to pay your vendors, and vendors can have multiple remit-to addresses for payments. For example, a vendor might supply an item from a subsidiary company, but wants to receive payment at their headquarters. [!INCLUDE [prod_short](includes/prod_short.md)] lets you set up multiple mailing addresses for each vendor, and you can choose the correct location to send payments to on an invoice-by-invoice basis.

You specify remit-to addresses on **Vendor Card** pages, and on the **Shipping & Payments** FastTab on purchase orders and invoices. The remit-to code on the vendor ledger entry is assigned when you create payment journal lines by using:

* The **Pay Vendor** or **Create Payment** actions on the **Vendors** list page or **Vendor Card** page.
* The **Apply Entries** action on a payment journal.

You can overwrite this value.

### To create a new vendor

[!INCLUDE[create_new_vendor](includes/create_new_vendor.md)]

> [!TIP]  
> If you don't know the invoicing address to be used for every invoice from a vendor, don't fill in the **No.** field on the **General** FastTab. Instead, choose the pay-to vendor number after you fill in a purchase quote, order, or invoice header.

The vendor is now registered, and the vendor card is ready to use on purchase documents.

If you want to use this vendor card as a template when you create new vendor cards, you can save it as a vendor template. Learn more in the [To save the vendor card as a template](#to-save-the-vendor-card-as-a-template) section.

### Deleting and editing vendor information

You can edit the information on vendor cards at any time. However, if you posted a transaction for a vendor, you can't delete the card because you might need the ledger entries for auditing. To delete vendor cards with ledger entries, contact your Microsoft partner to do so through code.

> [!TIP]
> You can change the International Bank Account Number (IBAN) on a vendor bank account without the change affecting your historical credit transfer register entries. Credit transfer register entries store the *Recipient IBAN* and the *Recipient Bank Account No.* specified in the **Vendor Bank Account** and **Recipient Name** fields from the **Vendor Card** page when the entries were created.

> [!TIP]
> You can add alternative addresses on vendor cards by choosing the **Order Addresses** action.

## To save the vendor card as a template

1. On the **Vendor Card** page, choose the **Save as Template** action. The **Vendor Template** page opens showing the vendor card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** page opens showing any dimension codes set up for the vendor.
4. Edit or enter dimension codes to apply to new vendor cards created using the template.
5. After you complete the new vendor template, choose **OK**.  
   The vendor template is added to the list of vendor templates. You can use it to create new vendor cards.

## Related information

[Merge Duplicate Records](sales-how-merge-duplicate-records.md)  
[Create Number Series](ui-create-number-series.md)  
[Set Up Vendor Bank Account](purchasing-how-set-up-vendors-bank-accounts.md)  
[Set Up Purchasers](purchasing-how-setup-purchasers.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Use Online Maps to Find Locations and Directions](across-online-maps.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
