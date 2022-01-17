---
title: Create a Vendor Card to Register a New Vendor (contains video)
description: In this topic learn how to create a vendor card to register a new vendor or supplier and save vendor cards as a template.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supplier
ms.search.form: 26, 27, 34, 786, 1379, 1385, 1386, 1628
ms.date: 09/29/2021
ms.author: edupont

---
# Register New Vendors

Vendors provide the products that you sell. Each vendor that you purchase from must be registered as a vendor card.

Before you can register new vendors, you must set up various purchase codes that you can select from when you fill vendor cards. When all of the required master data is created, you can perform additional configuration of the vendor, such as prioritize the vendor for payment purposes and list items that the vendor and other vendors can supply. Another group of setup tasks for vendors is to record your agreements concerning discounts, prices, and payment methods. For more information, see [Setting Up Purchasing](purchasing-setup-purchasing.md).

Vendor cards hold the information that is required to buy products from the vendor. For more information, see [Record Purchases](purchasing-how-record-purchases.md) and [Register New Items](inventory-how-register-new-items.md).

> [!NOTE]  
> If vendor templates exist for different vendor types, then a page appears when you create a new vendor card from where you can select an appropriate template. If only one vendor template exists, then new vendor cards always use that template.
<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE3PZtd?rel=0]

## Adding new vendors
You can add new vendors manually, by filling out the fields on the **Vendor Card** page, or you can use templates that contain predefined information. For example, you can create a templates for different types of vendor profiles. Using templates saves time when adding new vendors, and helps ensure that the information is correct each time. If you create templates for more than one type of vendor, you can choose the template to use when you add a vendor. If you create only one template it will be used for all new vendors. After you create a template, you can use the **Apply Template** action to apply it to one or more selected vendors. To create a template, you fill in the information that you want to reuse on the Vendor Card page, and then save it as a template. For more information, see [To save the Vendor Card page as a template](purchasing-how-register-new-vendors.md#to-save-the-vendor-card-as-a-template).

> [!TIP]
> It can be helpful to personalize the **Vendor Template** page when you create a template. For example, you might want to add a field that is not already displayed on the page. For more information, see [Personalize Your Workspace](/dynamics365/business-central/ui-personalization-user#to-start-personalizing-a-page-through-the-personalizing-banner).

You can also create a vendor from a contact. For more information, see [To create a customer, vendor, employee, or bank account from a contact](marketing-create-contact-companies.md#to-create-a-customer-vendor-employee-or-bank-account-from-a-contact). 

### To create a new vendor

[!INCLUDE[create_new_vendor](includes/create_new_vendor.md)]

> [!TIP]  
> If you do not know the invoicing address that will be used for every invoice from a vendor, do not fill in the **Vendor No.** field. Instead, choose the pay-to vendor number after you have set up a purchase quote, order, or invoice header.

The vendor is now registered, and the vendor card is ready to be used on purchase documents.

If you want to use this vendor card as a template when you create new vendor cards, you can save it as a vendor template. For more information, see the [To save the vendor card as a template](#to-save-the-vendor-card-as-a-template) section.

### Deleting and editing vendor information

You can edit the information on vendor cards at any time. However, if you have posted a transaction for a vendor, you cannot delete the card because the ledger entries may be needed for auditing. To delete vendor cards with ledger entries, contact your Microsoft partner to do so through code.

> [!TIP]
> You can change the IBAN on a vendor bank account without the change affecting your historical credit transfer register entries. Credit transfer register entries store the Recipient IBAN, Recepient Bank Account No. that were specified in the Vendor Bank Account and Recipient Name fields from the Vendor Card page when the entries were created.


## To save the vendor card as a template

1. On the **Vendor Card** page, choose the **Save as Template** action. The **Vendor Template** page opens showing the vendor card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** page opens showing any dimension codes that are set up for the vendor.
4. Edit or enter dimension codes that will apply to new vendor cards created by using the template.
5. When you have completed the new vendor template, choose the **OK** button.  
   The vendor template is added to the list of vendor templates, so that you can use it to create new vendor cards.

## See Also

[Merge Duplicate Records](sales-how-merge-duplicate-records.md)  
[Create Number Series](ui-create-number-series.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]