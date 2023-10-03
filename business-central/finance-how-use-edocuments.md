---
title: Using E-Documents in Sales and Purchase
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

# Using E-Documents in Sales and Purchase  

Once electronic documents are properly configured, they can be used with both sales and purchase documents.  

Currently you can use the following documents for electronic documents: Sales Invoice, Sales Order, Sales Credit Memo, Purchase Invoice, Purchase Order, Purchase Credit Memo, General Journals.  

 > [!NOTE]
 > **Purcahse Order** currently can be used only when you create the document from the electronic document from vendor, but this is not possible to update the existing document with the lines you got from your vendor.  

## E-Documents in Sales   

To create and send e-invoice to the customer, you need to create the sales invoice and post it (more details about standard process is here [Invoice Sales](sales-how-invoice-sales.md)). 

After postimg sales document, open the **Posted Sales Invoice** page to get access to the related **E-Document** page.

### Creating E-document in Sales

To see created e-document follow next steps:  

1. Run the **E-Document** action from the **Posted Sales Invoice** and choose the **Open E-Document** option.   
2. This will open up the **E-Document** page where you can see basic information about posted invoice in the header (posting and documen date, total amounts, customer information, document type...).  
3. The field **Record** showes exactly document number of the **Posted Sales Invoice** and you can click on this link to open this document.
4. You can also find the real-time status of document and where this document is in the process pipeline looking at the **Electronic Document Status** field; if this document is posted, status should be **Processed**.

### E-document Statuses and Logs in Sales

If you want to see more details about service status level of your e-document, you can look at the **E-Document Service Status** FastTab. In the lines, system will show one or more services this document used. The most common scenario is that one document uses one service, but it is also possible to have more of them.   

To see details about service status:  
1. Look at the **E-Document Service Code** field to see which service was used and to the **E-Document Status** field to see current service status for this document. 
2. If you want to go further to details, you need to click on the **Logs** field for this service to see chronological overview of different statuses changing for this document in the **E-Document Logs** page. 
3. At this page you can see **Entry No.** as well as **Created At** and some other invormetion for each of logs. When you look at the **E-Document Status** to check details, you will see that first status is **Exported** to show that e-document file has been created and after that **Sent** to show that document is sent to the service provider if configured. 

When you are positioned on the entry with the **Exported** status, you can run one of the following actions to get more insights:  

- **Open Mapping Logs** - for the overview of all exported fields from the sourced tables in the **Original Value**, but also the final value in the **New Value** field as you maybe used some transformation rules in the export process.  
- **Export File** - for exporting the xml file for manually review.   

But if you want to look at the communication betwwen you and the service you sending to your document, you can do it using the **Communitaion Logs** field. Openning the **E-Document Communication Logs** you can see details about the request and resons message with that service.  

If there is an issues with the service provider and document cannot be sent, you need to look again to the **E-Document** page and find the following messages:  

1. The **Electronic Document Status** field on the header will show the **Error** status.  
2. The **E-Document Status** on the **E-Document Service Status** FastTab will show the **Sending Error** status. 
3. If you look at the **Error and Warnings** FastTab, you will find one or more messages to show the root of this problem.
4. Once the problem has been resolved, you can manually run the **Send Document** actions.
5. If you need different actions from here you can eventually choose different actions here, as **Recreated Document**, **Cancel Document**, or **Get Approval**.  

## E-Documents in Purchase  

Receiving of purchase electronic invoices to Business Central can be done manually or as a batch job configuring the **Job Queue**.  

### Running the Batch Job 

 > [!NOTE]
 > This batching job for automated collection of your incoming invoices can work only if in your country this functionality exists. 

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
