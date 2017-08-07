---
    title: How to Post Service Credit Memos | Microsoft Docs
    description: When you have created a service credit memo and filled it in, you can post the credit memo. If there are errors or a lack of information on the credit memo while posting, the process will be interrupted by an error message.
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
# How to: Post Service Credit Memos
When you have created a service credit memo and filled it in, you can post the credit memo. If there are errors or a lack of information on the credit memo while posting, the process will be interrupted by an error message.  
  
### To post a service credit memo  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Credit Memos**, and then choose the related link.  
  
2.  Create a new service credit memo. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the necessary fields.  
  
4.  On the **Actions** tab, in the **Posting** group, choose **Post**. If you want to print the credit memo at the same time as you post, choose **Post and Print** instead.  
  
 To test credit memos before you post them,  choose **Test Report**. When you run the report, the posting dates specified in the document are verified, and so on.  
  
 To post several service credit memos at the same time. run the **Batch Post Service Cr. Memos** batch job. This can be an advantage if you have a large number of credit memos that must be posted.  
  
> [!NOTE]  
>  It is important to enter all the necessary information on the credit memos before they are batch posted. Otherwise, it is possible that they will not be posted. When the batch job has finished posting, a message is displayed that shows how many of the service credit memos have been posted.  
  
## See Also  
 [How to: Create Service Credit Memos](../how-to-create-service-credit-memos.md)   
 [How to: Print Test Reports Before Posting Service Documents](../how-to-print-test-reports-before-posting-service-documents.md)   
 [How to: Batch Post Service Orders](../how-to-batch-post-service-orders.md)