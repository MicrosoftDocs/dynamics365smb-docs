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
# Certificates of Supply
When you sell goods to a customer in another EU country\/region, the customer must confirm receipt before you can deduct VAT or calculate zero VAT according to the rules for intra-community trade.  
  
## Requiring a Certificate of Supply  
 When you sell goods or sell services that include items to a customer in another EU country\/region, you can post the order as shipped and invoiced. If a shipment requires a certificate of supply, you must print a certificate of supply that the customer must sign and return to you. According to the rules for intra-community trade, the invoice that you create at this point will not include VAT. Therefore, if the customer does not return the signed certificate of supply, you must issue a new invoice that includes VAT. Alternatively, you must manually correct the VAT.  
  
 You must print a certificate of supply if the shipment uses a combination of VAT business posting group and VAT product posting group that have been marked for requiring a certificate of supply in the VAT Posting Setup window.  
  
> [!TIP]  
>  You can add the relevant report to the report selection for sales, services, or return shipments so that the certificate of supply is printed automatically if it is required.  
  
 If the customer does not sign and return the certificate of supply, you must set the **Status** field to **Not Received**. Then, you must send the customer a new invoice that includes VAT and refers to the original invoice. This provides a trail that can help you in the auditing process.  
  
 To help you track if documents are posted that require a certificate of supply, you can enable the change log for the tables for shipments.  
  
 You can add a cue to your role center to show you documents that have a certificate of supply status of **Received** or **Not Received**. This way, it is easier for you to remind customers to return the certificate of supply so that you do not have to cancel the existing invoice and issue a new invoice.  
  
> [!NOTE]  
>  A certificate of supply is also required when you return a shipment to a vendor in another EU country\/region.  
  
## See Also  
 [How to: Process Certificates of Supply](../how-to-process-certificates-of-supply.md)   
 [Processing Sales Orders](../processing-sales-orders.md)   
 [How to: Enable the Change Log](../how-to-enable-the-change-log.md)