---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Understanding the VAT Rate Conversion Process
This topic describes the VAT rate change conversion process.  
  
## Understanding the VAT Rate Conversion Process  
 The following list defines the capabilities of the VAT rate change tool:  
  
-   Performs VAT rate conversions for master data, journals, and orders in different ways. The selected master data and journals will be updated by the new general product posting group or VAT product post group. If an order has been fully or partially shipped, the shipped items will keep the current general product posting group or VAT product posting group. A new order line will be created for the unshipped items and updated to align current and new VAT or general product posting groups. In addition, item charge assignments, reservations, and item tracking information will be updated accordingly.  
  
-   Will not convert sales or purchase orders and invoices where shipments have been posted. These documents are posted using the current VAT rate.  
  
-   Will not convert documents that have posted prepayment invoices. For example, you have made or received prepayments on invoices that have not been completed before you use the VAT rate change tool. In this case, there will be a difference between the VAT that is due and the VAT that has been paid in the prepayments when the invoice is completed. The VAT rate change tool will skip these documents and you will have to manually update them.  
  
-   Will not convert drop shipments or special orders.  
  
-   Wil not convert sales or purchase orders with warehouse integration if they are partially shipped or received.  
  
-   Will not convert service contracts.  
  
## See Also  
 [How to: Perform VAT Rate Conversions](../Finance/how-to-perform-vat-rate-conversions.md)