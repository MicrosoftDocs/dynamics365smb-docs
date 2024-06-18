---
author: brentholtorf
ms.topic: include
ms.date: 11/14/2023
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

The **Document Date** and **Posting Date** fields on sales and purchase documents helps you comply with accounting standards and get accurate financial calculations. The fields serve different purposes:

- For [!INCLUDE [prod_short](prod_short.md)] to correctly calculate finance charges and the amount due on sales invoices, the **Document Date** must align with one of the following dates:

   - The date on the sales invoice that you sent to the customer. 
   - The date on the purchase invoice that you received from your vendor.
- The **Posting Date** shows when a document was registered in [!INCLUDE [prod_short](prod_short.md)]. Many accounting standards and regulations require businesses to record and report financial transactions based on the date they occurred.

Depending on your business processes, these dates might or might not be the same. If they're the same, you can set up [!INCLUDE [prod_short](prod_short.md)] to update the document date on sales and purchase documents with the date you posted them.  
  
To automatically set document dates to posting dates, on the **Sales & Receivables Setup** and **Purchases & Payables Setup** pages, turn on the **Link Doc. Date to Posting Date** toggle.

> [!NOTE]
> The setting doesn't affect sales or purchase journals.