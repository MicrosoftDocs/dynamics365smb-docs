---
title: Create Invoices or Credit Memos for Services
description: Learn how to create invoices and credit memos for your services.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.search.keywords: service invoice, service credit memo, create service invoice, create service credit memo, post service invoice, post service credit memo
ms.topic: how-to
ms.date: 10/03/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Create service invoices or credit memos

Ease in invoicing your service orders is a key feature of [!INCLUDE[prod_short](includes/prod_short.md)]. You can set up your [!INCLUDE[prod_short](includes/prod_short.md)] so that a service technician in the field can create an invoice for a service that isn't connected to a contract or order. Alternatively, set up [!INCLUDE[prod_short](includes/prod_short.md)] so that you invoice service contracts periodically. The invoice period for each contract defines how often you invoice it.

## Invoice several service contracts

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Create Service Contract Invoices**, and then choose the related link.  
2. Set the filters you want to apply.  
3. In the **Posting Date** field, enter the date to use as the posting date on the service invoices.  
4. In the **Invoice to Date** field, enter the date up to which you want to invoice contracts. The batch job will include the contracts with the next invoice dates, up to this date.  
5. In the **Action** field, choose **Create Invoices**.  
6. Choose **OK** to create the service invoices.  
  
You can also invoice a service contract directly from the **Service Contract** page, if the next invoice date on the contract is earlier than the working date.

## Invoice a service contract from the Service Contract page

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Contracts**, and then choose the related link.  
2. Choose the service contract to invoice, and open the contract card.  
3. Choose **Create Service Invoice** action. 
4. Choose **Yes** to create the service invoices.  
  
  > [!NOTE]  
  > You can't create service invoices for the service contract when the **Change Status** field value is set to **Open**.  

## Post an invoice from a service order  

The following procedure describes how to define the part of service that you'll charge the customer for.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Choose the service order to invoice, and open the order card.  
3. Choose the **Service Lines** action.  
4. Find the required entries, and then specify the quantities for which you'll charge the customer in the **Qty. to Invoice** field.  
  
   > [!NOTE]  
   > You can invoice the customer for the registered service either fully or in parts. If you choose to invoice the customer fully, the value in the **Qty. to Invoice** field must equal the value in the **Quantity** field. You can post a full invoice together with a full shipment, and you can post a full invoice for an already posted full shipment that isn't invoiced or consumed.  
   >  
   > When you post a partial invoice, there are two ways of specifying the quantity to invoice. If you're going to post the service with **the Ship and Invoice** option, the value in the **Qty. to Invoice** field must equal the value in the **Qty. to Ship** field. If you want to invoice an already posted shipment, the quantity to invoice must not be larger than the value in the **Quantity Shipped** field.  
  
5. Choose **Post**, and then either **Invoice** or **Ship and Invoice**. Learn more in [Posting in Service Management](service-service-posting.md).  
  
 The service line you selected is posted. You can post several service lines at the same time by selecting them and choosing **Post**. If you do, make sure you fill in all the necessary information on the lines.  
  
 When you post the order with the **Invoice** option, a posted service invoice is created along with the corresponding ledger entries and updates to the relevant fields on the service lines of the order. Also, previously posted shipment documents are updated with the invoiced quantities. If you select the **Ship and Invoice** posting option, a posted shipment is created.

## Create a service invoice manually  

Typically, after you post a service order with the **Invoice** or **Ship and Invoice** option, a service invoice is posted automatically. Yet, you may need to issue an invoice that isn't linked to a service contract or order. This procedure explains how to issue an invoice at the same time that the customer receives the service.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Invoices**, and then choose the related link.  
2. Create a new service invoice.  
3. Fill in the **No.** field.  
  
    > [!NOTE]  
    > If you have set up number series for service invoices on the **Service Mgt. Setup** page, you can select **Enter** to select the next available service invoice number.  
  
4. In the **Customer No.** field, enter the number of a customer. Select the relevant customer from the list.  
  
    The customer fields are filled in with information from the **Customer** card.  
  
5. Enter a date in the **Posting Date** field. This date appears on the posted entries. This field shows your current work date, but you can change the date.  
6. In the **Document Date** field, enter a date that appears on the printed invoice and be used to calculate the due date.  
7. Fill in the service lines of the invoice. Fill in the **Type**, **No.**, and **Quantity** fields to register items, resources, and costs that have been used in servicing.

## Create an invoice that combines posted shipment lines from one or more service orders

You might need to create a service invoice for a service that's already shipped, either from one or several service orders, but not yet invoiced or consumed. You can fill in the invoice lines automatically with the selected posted shipment lines for a specific customer.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Invoices**, and then choose the related link.  
2. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 
3. Create invoice lines for services shipped but not invoiced. Alternatively, you can use the **Get Shipment Lines** action to add posted shipment lines to the invoice.  
4. Post the service invoice.  
  
 The posted service invoice and the corresponding ledger entries are created. Previously posted shipment documents update with the invoiced quantities and the quantities on the service lines of the source orders.  

## Create a service credit memo  

You typically use a service credit memo document when a customer returns an item. However, you can also use them to reimburse a customer or to correct an invoice that was a mistake.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Credit Memos**, and then choose the related link.  
2. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. The **Posting Date** and **Document Date** fields display the work date. If needed, you can change it.
4. On the credit memo lines, enter information about the items that have been returned or removed, or the compensation that will be given to the customer.  

## Correct errors in service invoices

You can delete service invoices that have service ledger entries associated with them. This means that you can correct errors or make changes to service invoices without getting stuck or losing data. For example, if you forget to assign a product posting group to a G/L account, you can add it later and recreate the service invoice.

Use the :::image type="content" source="media/copilot-delete-trash-can.png" alt-text="Delete action icon"::: action to delete a service invoice.

When you delete a service invoice, the following things happen:

* Post a corrective service ledger entry
* Restore the invoicing date and period in the contract, which lets you create the invoice again.

> [!NOTE]
> You can revert several invoices, but you must do so sequentially, starting from the last invoice.
>
> You can't delete a service invoice if its details, such as the invoicing period or the **Prepaid** toggle were changed in the related service contract. Make sure that you delete invoices before you change settings on the service contract.

## Related information

- [Post Service Invoices](service-how-to-post-service-orders.md)  
- [Setting Up Service Management](service-setup-service.md)  
- [Service Posting](service-service-posting.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]