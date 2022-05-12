---
title: Set up SII for VAT reporting [ES]
description: Learn how to set up Business Central to submit documents through SII  in the Spanish version.
author: SorenGP
    
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 10751, 10752, 10753, 10770, 10771
ms.date: 05/12/2022
ms.author: edupont

---
# Set Up SII for VAT Reporting in the Spanish Version

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the Spanish SII requirements for VAT reporting (Immediate Information Supply).  

## To use the SII module in the Spanish version

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SII Setup**, and then choose the related link.  
2. On the **General** FastTab, select the **Enabled** field.  

  The **Enabled** field is automatically selected if you import a certificate in the **Certificate Code** field on the **Certificate** FastTab.  
2. In the **Operation Date** field, specify if you want to use *Posting Date* or *Document Date* as the operation date in the XML file that will be sent through SII to the tax authorities.  
3. If you want to submit documents in batches, select the  **Enable Batch Submission** field.  

  <!--You must also specify how you want to submit them in the **Job Batch Submission Threshold** field, where you can specify the minimum number of pending history records for the batch submission.  -->

  If you not set up batch submissions, each document is submitted when you post the document, and the result is shown in the **SII History** page.  

  If you use batch submissions of documents, you can submit documents in batches manually or automatically. With automatic batch submission, documents are transferred to **SII History** with a status of *Pending* when you post them and submitted in batches when threshold value is met or exceeded, see the [Job batch submission thresholds](#job-batch-submission-thresholds) section.  
4. Configure other fields, import a valid certificate, and specify the relevant endpoints with the target URL.

## Job batch submission thresholds

If you want to use automatic batch submission, the **Job Batch Submission Threshold** field specifies the threshold number of documents with the status *Pending* that will trigger an automatic batch submission.

> [!IMPORTANT]
> Both the **Enabled** and the **Enabled Batch submission** fields must be selected for the threshold value to have effect.  

If the threshold is set to *0*, documents will be submitted when you post the document.  

If the threshold is set to *1* or more, documents are automatically submitted in batches. If the number of pending entries exceeds the threshold value, all pending entries are automatically submitted.  

You can always manually submit documents with a status of *Pending* by choosing the **Retry** or **Retry All** action.

## See Also

[SII - Invoice and Credit Memo Types in Sales and Purchase Documents](SII-invoice-types-sales-purchase-documents.md)  
[Spain Local Functionality](spain-local-functionality.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
