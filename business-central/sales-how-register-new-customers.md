---
title: Register New Customers by Creating a Customer Card
description: Describes how to create a customer card to register information about each new customer or client that you sell to.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: client, customer, credit
ms.date: 04/01/2021
ms.author: edupont

---
# Register New Customers

Customers are the source of your income. You must register each customer you sell to as a customer card. Customer cards hold the information that is required to sell products to the customer. For more information, see [Invoice Sales](sales-how-invoice-sales.md) and [Register New Items](inventory-how-register-new-items.md).  

Before you can register new customers, you must set up various sales codes that you can select from when you fill in customer cards. For more information, see [Setting Up Sales](sales-setup-sales.md).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3PZsM]

## Adding new customers

To register a new customer, you must fill in a customer card. You can establish templates for different customer profiles, or you can add customers without templates. You can also create a customer from a contact. For more information, see [To create a customer, vendor, employee, or bank account from a contact](marketing-create-contact-companies.md#to-create-a-customer-vendor-employee-or-bank-account-from-a-contact).  

> [!NOTE]  
> If customer templates exist for different customer types, then a page appears when you create a new customer card from where you can select an appropriate template. If only one customer template exists, then new customer cards always use that template.  

### To create a new customer card

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. On the **Customers** page, choose the **New** action.

    If only one customer template exists, then a new customer card opens with some fields filled with information from the template.

    If more than one customer template exists, then a page opens from which you can select a customer template. In that case, follow the next two steps.
3. On the **Select a template for a new customer** page, choose the template that you want to use for the new customer card.
4. Choose the **OK** button. A new customer card opens with some fields filled with information from the template.  
5. Proceed to fill or change fields on the customer card as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

On the **Sales Prices** FastTab, you can view special prices or discounts that you grant for the customer if certain criteria are met, such as item, minimum order quantity, or ending date. Each row represents a special price or line discount. Each column represents a criterion that must apply to warrant the special price that you enter in the **Unit Price** field, or the line discount that you enter in the **Line Discount %** field. For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).

The customer is now registered, and the customer card is ready to be used on sales documents.

If you want to use this customer card as a template when you create new customer cards, you can save it as a template. For more information, see the following section.  

### To save the customer card as a template

1. On the **Customer Card** page, choose the **Save as Template** action. The **Customer Template** page opens showing the customer card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** page opens showing any dimension codes that are set up for the customer.
4. Edit or enter dimension codes that will apply to new customer cards created by using the template.  
5. When you have completed the new customer template, choose the **OK** button.

The customer template is added to the list of customer templates, so that you can use it to create new customer cards.

## Deleting customer cards

If you have posted a transaction for a customer, you cannot delete the card because the ledger entries may be needed for auditing. To delete customer cards with ledger entries, contact your Microsoft partner to do so through code.  

## Managing credit limits

Credit limits, balance amounts, and payment terms make it possible for [!INCLUDE [prod_short](includes/prod_short.md)] to issue a credit and an overdue balance warning when you enter a sales order.  Furthermore, reminder term and finance charge term facilities allow you to invoice interest and/or additional fees.  

The **Credit Limit** field on a customer card specifies the maximum amount that you allow the customer to exceed the payment balance before warnings are issued. Then, when you enter information in journals, quotes, orders, and invoices, [!INCLUDE [prod_short](includes/prod_short.md)] tests the sales header and individual sales lines to see if the credit limit has been exceeded.

You can post even though the credit limit has been exceeded. If the field is left blank, there will be no credit limit for this customer.  

You can choose not to have warnings telling you that the customer's credit limit has been exceeded, and you can specify which types of warning you want to see.

### To specify credit limit warnings

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.

2. On the **General** FastTab, in the **Credit Warnings** field, choose the relevant option as described in the following table:

    |Option| Description|
    |------|------------|
    |**Both Warnings**| Both the **Credit Limit** and the **Balance Due** fields on the customer's card are checked, and a warning is shown if the customer has exceeded its credit limit or if the customer has an overdue balance.|
    |**Credit Limit**|The value in the **Credit Limit** field on the customer's card is compared with the customer's balance, and a warning is shown if the customer's balance exceeds this amount.|
    |**Overdue Balance**|The **Balance Due** field on the customer's card is checked, and a warning is shown if the customer has an overdue balance.|
    |**No Warning**|No warnings are shown about the customer's status.|

## See Also

[Defining Payment Methods](finance-payment-methods.md)  
[Merge Duplicate Records](sales-how-merge-duplicate-records.md)  
[Create Number Series](ui-create-number-series.md)  
[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
