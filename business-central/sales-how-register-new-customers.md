---
title: Register new customers by creating a Customer Card
description: Describes how to create a customer card to register information about each new customer or client you sell to.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: client, customer, credit
ms.search.form: 7, 21, 22, 33, 42, 43, 367, 368, 369, 461, 512, 785, 1330, 1380, 1381, 1382, 1627, 2107, 7177, 9080, 9081, 9084, 9301, 9305
ms.date: 05/19/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Register new customers

Customers are your source of income. You must register each customer you sell to as a customer card. Customer cards contain the information required to sell products to the customer. To learn more, go to [Invoice Sales](sales-how-invoice-sales.md) and [Register New Items](inventory-how-register-new-items.md).  

Before you can register new customers, you must set up various sales codes to choose from when you fill in customer cards. To learn more, go to [Setting Up Sales](sales-setup-sales.md).

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=37d3ec2a-71c2-4f0d-9a94-62c83805fbfa]

## Add new customers

You can add new customers manually by filling out the **Customer Card** page, or you can use templates that contain predefined information. For example, you can create a template for different types of customer profiles. Using templates saves time when adding new customers, and helps ensure the information is correct each time.

If you create:

* Multiple templates for use with more than one type of customer, you can choose the suitable template when you add a customer.
* Only one template is used for all new customers.

After you create a template, you can use the **Apply Template** action to apply it to one or more selected customers. To create a template, fill in the information to be reused on the **Customer Card** page, then save it as a template. To learn more, go to [To save the customer card as a template](sales-how-register-new-customers.md#to-save-the-customer-card-as-a-template).

> [!TIP]
> It can be helpful to personalize the **Customer Template** page when you create a template. For example, you might want to add the **Credit Limit** field to a template. To learn more, go to [Personalize your workspace](/dynamics365/business-central/ui-personalization-user#start-personalizing-by-using-the-personalization-mode).

You can also create a customer from a contact. To learn more, go to [Create a customer, vendor, employee, or bank account from a contact](marketing-create-contact-companies.md#create-a-customer-vendor-employee-or-bank-account-from-a-contact).  

### To create a new customer card

[!INCLUDE[create_new_customer](includes/create_new_customer.md)]

The **Prices & Discounts** action provides options for managing special prices or discounts for a customer when an order meets certain criteria. When purchasing a certain item, ordering a minimum quantity, or buying before a date, such as when a campaign ends, are examples of such criteria. To learn more, go to [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).

The customer is now registered, and the customer card is ready to be used on sales documents.  

### To save the customer card as a template

You can use a customer card as a template when you create new customer cards.

1. On the **Customer Card** page, choose the **Save as Template** action. The **Customer Template** page opens showing the customer card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** page opens showing any dimension codes set up for the customer.
4. Edit or enter dimension codes you want to apply to new customer cards created with this template.  
5. When you complete the new customer template, choose **OK**.

The customer template is added to the list of customer templates, and you can use it to create new customer cards.

## Delete customer cards

If you post a transaction for a customer, you can't delete the customer card because the ledger entries might be needed for auditing. To delete customer cards with ledger entries, contact your Microsoft partner to do so through code.  

## Manage credit limits

Credit limits, balance amounts, and payment terms make it possible for [!INCLUDE [prod_short](includes/prod_short.md)] to issue a credit and an overdue balance warning when you enter a sales order. Furthermore, reminder term and finance charge term elements enable you to invoice interest and/or extra fees.  

The **Credit Limit** field on a customer card specifies the maximum amount you allow the customer to exceed the payment balance before warnings are issued. When you enter information in journals, quotes, orders, and invoices, [!INCLUDE [prod_short](includes/prod_short.md)] tests the header and lines to determine whether the document exceeds the credit limit.

You can post even if the credit limit exceeds. A blank field means there's no credit limit for this customer.  

You can choose not to receive warnings when the customer's credit limit is exceeded, and you can specify which types of warnings you want to see.

### To specify credit limit warnings

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales & Receivables Setup**, then choose the related link.

2. On the **General** FastTab, in the **Credit Warnings** field, choose the relevant option as described in the following table:

    |Option| Description|
    |------|------------|
    |**Both Warnings**| Both the **Credit Limit** and the **Balance Due** fields on the customer's card are checked, and a warning is shown if the customer exceeds its credit limit or has an overdue balance.|
    |**Credit Limit**|The value in the **Credit Limit** field on the customer's card is compared with the customer's balance, and a warning is shown if the customer's balance exceeds this amount.|
    |**Overdue Balance**|The **Balance Due** field on the customer's card is checked, and a warning is shown if the customer has an overdue balance.|
    |**No Warning**|No credit warnings are shown regarding the customer's status.|

## Assign a salesperson

You can assign salespeople to customer ship-to address rather than their billing address so your sales reports reflect the true geographical distribution of your sales. Assigning a salesperson to a customer's ship-to address gives you more precise insights and optimizes resource allocation.

Assign a salesperson on the **Customer** card page by choosing **Customer**, and then **Ship-To Addresses** to open the **Ship-to Addresses List** page. Choose **Manage**, and then **Edit** to open the **Ship-to Address** card page. Enter or choose a **Salesperson Code** to select the salesperson.

When you choose the **Alternate Shipping Address** option as a **Ship-To** location on a sales document, the **Salesperson Code** updates to match the salesperson from the **Ship-to** rather than the **Bill-to** address.

## Related information

[Defining Payment Methods](finance-payment-methods.md)  
[Merge Duplicate Records](sales-how-merge-duplicate-records.md)  
[Create Number Series](ui-create-number-series.md)  
[Enable Partial Shipments with Shipping Advice](sales-how-send-partial-shipments.md)  
[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Use Online Maps to Find Locations and Directions](across-online-maps.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
