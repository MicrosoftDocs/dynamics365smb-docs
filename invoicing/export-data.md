---
title: Export data | Invoicing
description: Learn how to export data, such as deleting contacts as part of a data subject request.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/08/2019
ms.author: bholtorf

---
# Export or delete data from [!INCLUDE[d365inv_long](includes/d365inv_long.md)]
> [!Note]
> [!INCLUDE[d365inv_discont](includes/d365inv_discont.md)]

## Export all of your data
If you are an administrator, [!INCLUDE[d365inv](includes/d365inv.md)] provides an assisted setup guide that lets you export data for customers, prices, invoices, estimates, and payments to Excel, all in one go, and send the workbook to an email address. The Excel workbook will list the information on separate tabs. You can start the guide in two ways:

* When you sign in, a notification displays. Start the guide by choosing **Export**.
* On your Role Center, under **Important News**, choose **Next steps**.    

> [!Note]
> Only system administrators can export data from [!INCLUDE[d365inv](includes/d365inv.md)].

## Export invoices only
If you just want to export invoices, on the **Invoices** list page, choose **Manage** and then **Export invoices**. Enter start and end dates for the period to export invoices for, and make sure that the correct email address is entered. Invoicing will export the documents to Excel, and then send the workbook to the email address.

## Delete an existing customer
If you want to delete a contact or customer from [!INCLUDE[d365inv](includes/d365inv.md)], it's easy to do.
1. On your Home page, choose **Customers** to open the list of customers.
2. Find the contact, and then choose the name to open the details.
3. Choose the **Delete** action.

> [!NOTE]
> If you have already sent them an invoice, you cannot delete the customer. Instead, [!INCLUDE[d365inv](includes/d365inv.md)] can mark the customer as blocked for further business. That means that you cannot send them new invoices, for example.  

If the contact has not been added as a customer, you can add them by creating a draft invoice.

## Add a contact as a customer and then delete the customer
1. On your Home page, choose **New Invoice**
2. In the **Customer Name** field, start typing the contact’s name.
3. Select your contact from the look-up, and then tab out.
4. Delete the draft invoice that was just created.
5. Follow the steps for deleting the customer as described above.

## See also
[Set up your business information](set-up-business-profile.md)  
[Send an invoice to a new customer](send-invoice.md)  
[Troubleshooting](about-troubleshooting.md)  
