---
title: Set up SII for VAT reporting [ES]
description: Learn how to set up Business Central to submit documents through SII in the Spanish version.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 10751, 10752, 10753, 10770, 10771, 747, 473
ms.date: 07/12/2022
ms.author: edupont

---
# Set Up SII for VAT Reporting in the Spanish Version

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the Spanish SII requirements for VAT reporting (Immediate Information Supply).  

## Enable the SII module in the Spanish version

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SII Setup**, and then choose the related link.  
2. On the **General** FastTab, select the **Enabled** field.  

   The **Enabled** field is automatically selected if you import a certificate in the **Certificate Code** field on the **Certificate** FastTab.  
3. In the **Operation Date** field, specify if you want to use *Posting Date* or *Document Date* as the operation date in the XML file that is sent through SII to the tax authorities.  
4. If you want to submit documents in batches, select the **Enable Batch Submission** field.

   If you do not enable batch submissions, each document is submitted when you post them, and the result is shown on the **SII History** page.

   If you use document batch submissions, you can submit documents in batches manually or automatically. With automatic batch submission, documents are transferred to the **SII History** page with a status of *Pending* when you post them and submitted in batches when the threshold value is met or exceeded. Learn more in the [Job batch submission thresholds](#job-batch-submission-thresholds) section.
5. Configure the other fields, import a valid certificate, and specify the relevant endpoints with the target URLs. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## Job batch submission thresholds

If you want to use automatic batch submission, the **Job Batch Submission Threshold** field specifies the threshold number of documents with the status *Pending* that will trigger an automatic batch submission.

> [!IMPORTANT]
> Both the **Enabled** and the **Enabled Batch submission** fields must be selected for the threshold value to have effect.  

If the threshold is set to *0*, documents will be submitted when posted.

If the threshold is set to *1* or more, documents are automatically submitted in batches. When the number of pending entries exceeds the threshold value, all pending entries are automatically submitted.  

You can always manually submit documents with a *Pending* status by choosing the **Retry** or **Retry All** actions on the **SII History** page.

## Specify customers without a registered NIF with AEAT

If a customer's NIF number is not yet registered in the AEAT database, document submissions will be rejected. In this case, you can select the **Not in AEAT** option and resubmit the document.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. Choose the relevant customer to open the **Customer Card**.
3. Select the **Not in AEAT** field.

## Set VAT exemptions

To indicate value-added tax (VAT) exemptions under the SII scheme you can either select an exemption code for a VAT clause on the **VAT Clauses** page, or you can create a new clause that corresponds to the exemption and choose the appropriate code in the **SII Exemption Code** field.

>[!IMPORTANT]
>The default values are provided to cover standard scenarios. Your business and type of business transactions and any customization you may have may require you to select a different value to meet the reporting requirements under SII.

To enable reporting on **Non Taxable Due To Localization Rules** scenarios, set the appropriate **VAT Posting Setup Card** on the **VAT Posting Setup** page by choosing the option in the **No Taxable Type** field.

## See also

[SII - Invoice and Credit Memo Types in Sales and Purchase Documents](SII-invoice-types-sales-purchase-documents.md)  
[Spain Local Functionality](spain-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
