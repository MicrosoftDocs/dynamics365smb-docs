---
title: Use e-documents in the purchase process
description: Learn how to use e-documents functionality that is related to purchase invoices and orders.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, receive, purchase, matching, mapping, Copilot
ms.search.form: 50, 51, 138, 6103, 6133, 6121, 6167, 9307, 9308
ms.date: 03/26/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Use E-documents in the Purchases Process

You can use configured electronic documents (e-documents) with the purchase documents.

You can use the following purchaes documents with e-documents functionality:  

- Purchase invoices
- Purchase orders (from version 24.0)
- Purchase credit memos
- General journals

> [!NOTE]
> From Business Central version 24.0, it is possible to connect **Purchase Orders** with received **E-Documents**.  

## E-documents in Purchases

The receipt of purchase electronic documents in Dynamics 365 Business Central can be done as a batch job or manually.  

### How to Set Up Vendors to Work with Different Purchase Documents  

Follow the next steps to configure vendors to work properly with incoming electronic invoices: 

1.	Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then select the related link. 
2.	Choose the vendor you want to configure.   
3.	In the **Receiving** FastTab, find the **Receive E-Document To** field to specify the default purchase document to be generated from received E-document. 

> [!NOTE]
> In the **Receive E-Document To** field users can select either a **Purchase Invoice** or **Purchase Order** type of document based on what they would like to have created from received e-invoice. This selection does not affect the creation of corrective documents; in both scenarios, the system will generate a **Credit Memo**.  

> [!NOTE]
> If the user chooses the **Purchase Order** option in the **Receive E-Document To** field, the system will try to update one of existing purchase orders, but if the purchase order for the vendor in the received **E-Document** does not exist, Business Central will create a new **Purchase Order**, using the same approach as creating new **Purchase Invoices** explained in this page later.  

4.	Choose one of the options you want to use for the selected vendor. 
5.	Close the page.   

### Working with Purchase Invoices  

#### Run the Batch Bob  

> [!NOTE]
> This batch job is for automated collection of your incoming invoices. It can work only in a country or region where the functionality exists.  

Every time that a **Job Queue** is run, if the external service has incoming invoices that were sent from your vendor, the system collects and imports those invoices. To complete the process, follow these steps. 

1. After the batch job has been finished running, the newly imported invoices are listed on the **E-Documents** page, together with their basic detail information. 
2. To view more details, open a specific e-document.   
3. If there were no errors or issues in the e-document and its mapping, the **Record** field shows the document number of the purchase invoice, if this is configured on the vendor card, that the system automatically created. Select the link to open the document. This system-created document isn't the posted document. 
4. To go directly to the purchase document, select the **Record** field. After you open the **Purchase Invoice** page, check the document. Then, if everything is correct, post the document.  
5. When you post the purchase document, the **Record** field on the **E-Document** is updated from **Invoice** to **Purchase Invoice**, and the number of the posted purchase document is available. You can select the number to open the posted purchase invoice. 

Details about logs are the same as they are in the sales process for e-documents.  

Because errors in the sales process are mostly related to the availability of the service, the incoming document can contain multiple reasons. The most common reason for an error is that system can't recognize the lines on the e-document that you got from your vendor. Therefore, it can't enter lines in your purchase invoice. 

There are two common errors:  

- If you want to use this specific line from your vendor invoice that was directly posted to the general ledger (G/L) account, you must have correctly configured the **Mapping Text** value. To bypass this error if you want to use G/L accounts, select **Map Text to Account** to create a specific mapping of the **Mapping Text** value with the **Debit Acc. No.** value that you want to use. 
- If you want to track the inventory and use lines from your vendor invoice to fill in items on your document lines, you must have correctly configured the **Item Reference No.** value. To bypass this error, map the external item with your item numbers by using the item reference list. To learn more, see [Use Item References](inventory-how-use-item-cross-refs.md). 

After you fix the errors and warnings, you can manually specify when the system should create a purchase invoice based on your setup by selecting **Create Document**.   

#### Manually Import Invoices  

To manually import external e-documents, follow these steps. 

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Service**, and then select the related link. 
2. On the **E-Document Service** page, select the active service.   
3. Select **Receive**, and upload the e-document file that you got from the vendor. 
4. If an error message occurs, open the e-document to fix the issues. 
5. When you've finished fixing issues, in the **Import Manually** group, select **Create Document**.  
6. After the document is created in Business Central, you can view it just as you do if you use a batch job. 

### E-Documents with Purchase Orders  

#### Linking Purchase Orders with Received E-Documents

If your **Vendor** has configured the **Receive E-Document To** field to work with **Purchase Orders**, once electronic document is created in Business Central (manually or from external end point), Business Central will do the following:  

1.	If the **Purchase Order** for this particular vendor exists and there is a purchase order number in the receive **E-Document** file, Business Central will automatically link this **E-Document** with the mentioned **Purchase Order**, and the **Document Status** of this **E-Document** will be **In Progress**, and the **E-Document Status** in the **Service Status** subpage will be **Order linked**. This link will be visible in the **Document** field on this specific **E-Document**. If you need to change the **Purchase Order** linked automatically, you can do it using the **Update Purchase Order Link** action and choose manually one of existing purchase orders for this vendor. You can do it only before matching lines between **E-Document** and **Purchase Order**.  
2.	If the **Purchase Order** for this particular vendor exists but there is no a purchase order number in the receive **E-Document** file, Business Central will offer possibilities to choose one of existing purchase orders when and if you uploaded this document manually, opening the **Purchase Orders** list with orders only for the vendor you got **E-Document**, where you need to select **Purchase Order** you want and click the **OK** button. If you didn’t select the proper **Purchase Order**, or you got the **E-Document** automatically from external end point using the **Job Queue**, new **E-Document** will not be linked with any purchase document and the **Document Status** will be **Error** and the **E-Document Status** in the **Service Status** subpage will be **Imported document processing error**. To finish linking with the **Purchase Order**, select the **Update Purchase Order Link** action and choose one of existing purchase orders for this vendor. 
3.	If the **Purchase Order** for this particular vendor doesn’t exist in the moment of creation new **E-Document**, Business Central will create a new **Purchase Order**, using the same model of creation as already exists for new **Purchase Invoices**. The **Document Status** of this **E-Document** will be **Processed**, and the **E-Document Status** in the **Service Status** subpage will be **Imported document created**. This link will be visible in the **Document** field on this specific **E-Document**.   

#### Matching Lines from received E-Document with Purchase Order  

You can match your received electronic documents with purchase orders’ lines from two different places, from the **E-Document** page or from the **Purchase Order** page. The easiest way to locate already linked **Purchase Orders** is to use the **Linked Purchase Orders** tile as a part of **E-Document Activities**. All non-linked documents can be found using the tile **Waiting Purchase E-Invoices** where you have a list of **E-Documents** requiring your reviewing.  

> [!NOTE]
> The **E-Document Activities** with these two tiles can be found in the next **Role Centers**: Business Manager Evaluation, Business Manager, Accountant, Inventory Manager, and Shipping and Receiving.  

> [!NOTE]
> It is not possible to use matching documents in multicountri environment if VAT percentage differs from incoming document with VAT percentage in the company.  

##### Matching Lines from Purchase Order  

You can match the lines from the **Purchase Orders** list or from one opened **Purchase Order**. To start with this, use the following steps:  

1.	Click on the **Linked Purchase Orders** tile on your Role Center if there is any number. 
2.	As there are two options for matching, choose one of them: 

    1. If you want to match lines from the **Purchase Orders** list, select the** Purchase Order** line you want to match and click the **Map E-Document Lines** action.  
    2. If you want first to open the **Purchase Order**, open the document, and then click the **Map E-Document Lines** action. 

3.	As both options have the same process, you will open the **Purchase Order Matching** page with the following content: 

  	1. In the header you can find the next information which can help you to map the lines easier: 

    |Field name |Description |
    |--------|-----------------|
    |Vendor Name |Specifies the vendor’s name of the electronic document. |
    |E-Document No. |Specifies the linked electronic document number. |
    |E-Document Date |Specifies the linked electronic document date.  |
    |E-Document Amount |Specifies the linked e-document total amount including VAT. |

    2. In the lines you can find lines imported from the **E-Document** file on the left side and the lines from existing **Purchase Order** on the right side.  
    3. All lines from both sides have item numbers and descriptions, together with the **Direct Unit Cost** and **Line Discount %**.  
    4. On the **Imported Lines** side, you can also locate the **Quantity** field as a total quantity from e-invoice and the **Matched Quantity** field specifying the quantity that already matched to purchase order lines. 
    5. On the **Purchase Orders Lines** side, you can also find the **Available Quantity** as the quantity that can be matched to this line (received, but not invoiced quantity) and **Qty. to Invoice**, specifying the quantity that is already matched to this line. 
    6. To match lines, select the lines from both sides you want to match and click the **Match Manually** action. The matched lines will be marked with the green color. 
    7. It is possible to match one to one, but it is also possible to match many to one or one to many, selecting more lines on one or another side before clicking the **Match Manually** action. 
    8. You can also use the **Match Automatically** action to automatically match all lines with the same **Type**, **No.**, **Unit Price**, **Discount** and **Unit of Measure**. 
    9. If you make a mistake, you can run the **Remove Match** action to remove matched lines from purchase order side or the **Reset Matching** action to reset all matching. 
    10. If your **E-Document** has many lines, during matching process, you can use the **Show Pending Lines** action to remove all e-document lines if they are already completely matched. If you need to see all the lines, you can always run the **Show All Lines** action. 

4.	Once you finish the matching, you need to run the **Apply To Purchase Order** action.   
5.	Once you apply the matching to the **Purchase Order**, Business Central will update the following fields:

    1. **Vendor Invoice No.** and **Document Date** on the document header will be updated with values from the electronic document you received and linked. 
    2. **Qty. to Invoice** in lines will be updated with the values from the **Qty. to Invoice** column from the **Purchase Order Matching** page based on matching you did. 
    3. Now you can post the document, running the **Post** action.  
    4. Once you post the document, the **Document** field in the **E-Document** page will change the value and it will relate to the **Posted Purchase Invoice**. 
    5. Close the page.  

> [!IMPORTANT]
> By default, you can match only the lines where the total amount is the same in both documents. That means **Direct Unit Cost** together with applied Line **Discount %** must be the same, as in one document you can have amount without discount and in another with discount.  

If you want to add some tolerance and allow the difference between lines in **E-invoice** and **Purchase Order**, follow the next steps:   

1.	Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then select the related link.  
2.	At the tolerance you want to allow in the **E-Document Matching Difference %** field, specifying the maximum allowed percentage of cost difference when matching incoming **E-Document** line with **Purchase Order** line. 
3.	This setup will apply to all matching lines, but again considering tolerance for the total amount, as for **Direct Unit Cost** together with applied **Line Discount %**.  
4.	Close the page.   

##### Matching Lines from E-Document  

You can match the lines from the **E-Document** page. To start with this, use the following steps:  

1.	Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Documents**, and then select the related link. 
2.	Select the **E-Document** you want to match.   
3.	Run the **Match Purchase Order** action to open the **Purchase Order Matching** page.  
4.	Repeat the same steps you used when you started matching from purchase orders.

### Using the E-Document Matching Assistance copilot  

> [!NOTE]
> In this moment the **E-Document Matching Assistance** copilot is in the Production ready preview status, and it is available globally except in Canada. But it works in English only. 

> [!NOTE]
> Copilot is the AI-powered assistant that helps people across your organization unlock their creativity and automate tedious tasks. The **E-Document Matching Assistance** copilot helps users to easier match their received electronic invoices with existing purchase order lines, using LLM model for matching lines between two different documents. 

#### Activating the Copilot  

In case you do not have activated **E-Document Matching Assistance** copilot, you need to do it manually. To enable the **E-Document Matching Assistance** copilot, follow the next steps: 

1.	Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Copilot & AI Capabilities**, and then select the related link. 
2.	In the list of capabilities choose **E-Document Matching Assistance** and change the status to **Active**.  

Once you activate this Copilot, you can start using it.

#### Use the E-Document Matching Assistance Copilot 

If the Copilot is activated, existing actions **Map E-Document Lines** on purchased orders and **Match Purchase Order** on the **E-Document** page will get different icons, symbolizing AI capability. You can run these actions absolutely the same as in previous examples from the list of purchase orders, from one **Purchase Order**, or from **E-Document**. All steps for running are the same, but when you run this action, the result will be different, and you need to follow next steps:  

1.	Run the **Map E-Document Lines** or **Match Purchase Order** action, for already linked documents.  
2.	You can notice that **E-Document Match Order Lines with Copilot** prompt is working and that you have the **Purchase Order Matching** page in the background. That means the same process is happening but with the automatic support of **Copilot**, who runs the process of matching instead of you. 
3.	After a few seconds, the **E-Document Match Order Lines with Copilot** will suggest lines for matching with some additional details: 

    1. In the prompt header, you can find the following information: 

    |Field name |Description |
    |--------|-----------------|
    |Auto-matched | Specifies the number of matches proposed automatically. This is based on a string comparison and if there is 80% or more description overlapping, the system will match these descriptions automatically without using GPT capabilities. |
    |Copilot matched | Specifies the number of matches proposed by Copilot using both string and semantical comparison. |
    |E-Document No. | Specifies the linked E-Document number. |
    |Invoice Total Amount Excl. VAT | Specifies the total invoice amount excluding VAT. |
    |Matched Total Amount Incl. VAT | Specifies the matched amount excluding VAT. |
    
    2. If all lines are matched, you will see the green text in the upper right corner: **All lines (100%) are matched. Review match proposals**.  
    3. In the **Matched proposal** lines, you can find the following information:  

    |Field name |Description |
    |--------|-----------------|
    |E-Document Line No. | Specifies the E-Document line number (coming from original e-document file). |
    |E-Document Line Description | Specifies the E-Document line description (coming from original e-document file). |
    |Matched Quantity | Specifies the quantity that will be applied to purchase order line. |
    |Proposal | Specifies the action proposed by AI, and these suggested actions are related to matching purchase order lines. |

    4. All fully suggested and matched lines are marked with green color. If there is some issue, i.e. different price, but in the allowed price range, this line will be marked as yellow, and if there is a similarity between description but price difference bigger than allowed, this line will be marked as red. 
    5. If you are not satisfied with some suggestions, you can delete them using the **Delete Line** action.  
    6. If you want to see proposal matchings, you can click on the link in the **Proposal** column to open the **E-Document Match Det**ails page. 
    7. On the **E-Document Match Details** page you can compare details from **E-Document** and **Purchase Order**, to be sure about suggested matching before confirming it. 
    8. After reviewing, close the page.   

4.	If you are not satisfied with most of the suggestions, or in a case you do not want to use the **E-Document Match Order Lines with Copilot** feature, click on the **Discard it** button, and you can continue with the manual matching as explained previously.  
5.	If you want to keep suggestions, choose the **Keep it** button and the system will save all suggestions made by **Copilot**.  
6.	Business Central will close the Copilot prompt and lines in the **Purchase Order Matching** page will be marked as green, as they are already matched.  
7.	From this moment, you can continue to work as you are doing manual matching, and that means you can remove matches, manual matches, reset matching or if there are no changes you want to make, just select the **Apply To Purchase Order** action and continue working with the **Purchase Order**. 

> [!NOTE]
> If you want you can run **Match with Copilot** action from the **Purchase Order Matching** page again, but in this case, you will be asked if you want to overwrite the existing matches, as all lines are already matched.  

> [!NOTE]
> Price/Cost analyze, and the available quantity check is part of preprocessing activity.   

## Overview of e-document statuses

To get a better overview of all e-documents in the company, you can select the **Accountant** role center where e-document statuses exist. There, you can find e-document activities that have the following statuses:

- **Incoming e-documents:**

    - Processed
    - In Progress
    - Error


## See also

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)  
[How to use e-document in the sales process](finance-how-use-edocuments.md) 
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]

