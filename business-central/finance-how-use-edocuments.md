---
title: Use E-Documents in Sales and Purchase
description: Learn how to use E-Documents functionality related with sales and purchase invoices.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, sales, purchase
ms.search.form: 42, 43, 51, 6103, 6133, 6121, 9301, 9305, 9308
ms.date: 10/03/2023
ms.author: altotovi
---

# Use E-Documents in Sales and Purchase  

You can use configured electronic documents with sales and purchase documents.  

Currentl,y you can use the following documents for electronic documents: 

 - Sales Invoice
 - Sales Order
 - Sales Credit Memo
 - Purchase Invoice
 - Purchase Order
 - Purchase Credit Memo
 - General Journals  

Currently, a Purcahse Order can only be used when you create the document from the electronic document from vendor, but it isn't possible to update the existing document with lines you got from your vendor.  

## E-Documents in Sales   

To create and send an e-invoice to the customer, you need to create and post the sales invoice. To learn more about the standard process, see [Invoice Sales](sales-how-invoice-sales.md). 

After you post the sales document, open the **Posted Sales Invoice** page to access the related **E-Document** page.

### View E-document in Sales

To view existing e-documents, follow these steps. 

1. On the **Posted Sales Invoice** page, select **E-Document** > **Open E-Document**.   
2. On the **E-Document** page you can see basic information about the posted invoice in the header. 
3. The **Record** field shows the document number of the **Posted Sales Invoice**. Select the link to open the document.
4. You can also find the real-time status of document and where the document is in the process pipeline in the **Electronic Document Status** field. If the document is posted, the status is **Processed**.

### E-document Statuses and Logs in Sales

For details about the service status level of your e-document, check the **E-Document Service Status** FastTab. In the lines, the system shows one or more services the document used. The most common scenario is that one document uses only one service, but it's possible to have more.   

- Check the **E-Document Service Code** field to determine which service was used.
- Check the **E-Document Status** field to see the current service status for this document.
- If you want more details, select the **Logs** field for this service on the **E-Document Logs** page for a chronological overview of the different statuses for this document.
- Check the **Entry No.** and **Created At** fields as well as other information on the **E-Document Logs** page. In the **E-Document Status** field, the first status is **Exported** to show that the e-document file has been created. The next status is **Sent** to show that document is sent to the service provider if configured. 

For more insights, select the entry with the **Exported** status and run one of the following actions:  

- **Open Mapping Logs** - Get an overview of all exported fields from the sourced tables in the **Original Value**. You can also get the final value in the **New Value** field if you used transformation rules in the export process.  
- **Export File** - Export the xml file for manual review.   

To look at the communication betwwen you and the service you are sending your document to, use the **Communitaion Logs** field. Open the **E-Document Communication Logs** to view details about the request and reasons message with that service.  

If there is an issue with the service provider and the document can't be sent, look for the following messgaes on the **E-Document** page. 

- The **Electronic Document Status** field on the header shows the **Error** status.  
- The **E-Document Status** on the **E-Document Service Status** FastTab shows the **Sending Error** status. 
- The **Error and Warnings** FastTab contains one or more messages that provide the root of thw problem.

After the problem is resolved, manually run the **Send Document** actions. If you need different actions, you can select different actions including **Recreated Document**, **Cancel Document**, or **Get Approval**.  

## E-Documents in Purchase  

Receipt of **Purchase** electronic invoices to Dynamics 365 Business Central can be done manually or as a batch job.  

### Run the Batch Job 

 > [!NOTE]
 > This batch job is for automated collection of your incoming invoices and can work only in your country where the functionality exists. 

Everytime **Job Queue** run and if there were incoming invoices in the external service sent from your vendor, system will collect them and import to the system. To complete the process follow next steps:  

1. After batch job has been finished, you will find new imported invoices in the **E-Documents** page with the basic details in the list.
2. To see more details you need to open the specific **E-Document**.
3. If there were no errors and other issues in the electronic document and its mapping, the field **Record** showes exactly document number of the **Purchase Invoice** system automatically created and you can click on this link to open this document. This created document is not posted document.
4. If you want to go directly to this purchase document, you just need to click on the **Record** field. Once you open the **Purchase Invoice** you can check the document and if everything is correct, you can post the document.
5. When you post the purchase document, the **Record** field in the **E-Document** will update the value from **Invoice** to the **Purchase Invoice** and number will now show the number of posted purchase document. If you click on this link now, it will lead you to the **Posted Purchase Invoice**.  

Details about logs are the same as they exists in the sales process of e-documents.   

As errors in the sales process are mostly related with the availability of the service, in the incoming document there can be more reasons. The most common reason is that system cannot recognize the lines from the electronic document you got from the vendor and it was not possible to populate lines in your **Purchase Invoice**.  

There are two the most common errors:  

- If you want to use this specific line from your vendor invoce directly posted to the G/L Account, you must have properly configured **Mapping Text**. To bypass this error if you want to use **G/L Accounts**, you need to run the **Map Text to Account** action to create specific mapping of the specific **Mapping Text** with the **Debit Acc. No.** you want to use.  
- If you want to track the inventory and to use lines from your vendor invoice to fill in items in your document lines, you must have properly configured **Item Reference No.**. To bypass this error, you need to map external item with your item numbers using the **Item Reference List** (more details here: [Use Item References](inventory-how-use-item-cross-refs.md)).

After resolving errors and warnings you can process manually, running the **Create Document** actions, when system will create purchase invoice based on your set up.

### Manually Invoices Import 

To import the external electroni document you have got to the system manually, you need to follow these steps: 

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Service**, and then choose the related link.
2. Open the **E-Document Service** page and choose the service you have as an active. 
3. Run the **Receive** action and upload e-document file you got from the vendor.   
4. If the error message appears you can open the **E-Document** to resolve issues, using the same instructions we provided in the previous topic.
5. If there were errors, after you resolved all error messages, run the **Import Manually** action group and run the **Create Document** action.
6. Aftre creation of the document in Business Central, you can proceed to this document the same way as we previously explained when you used a batch job.  

## Overview of E-Document Statuses 

To have better overview of all e-documents in the company, you can choose **Accountant** role center where e-document statuses exist. You can find **E-Document Activities** with the following statuses there:  
- Outgoing E-Documents:
   - Processees
   - In Progress
   - Error
- Incoming E-Dcouments:
   - Processees
   - In Progress
   - Error
 

## See also

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md) 
[How to extend e-documents in Business Central](finance-how-extend-edocuments.md)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md) 
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
