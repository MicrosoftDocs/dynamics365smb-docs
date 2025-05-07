---
title: Set up SII for VAT reporting [ES]
description: This article explains how to submit documents through SII in the Spanish version of Microsoft Dynamics 365 Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.form: 10740, 10751, 10752, 10753, 10770, 10771, 747, 473, 472
ms.date: 04/25/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set Up SII for VAT Reporting in the Spanish Version

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the Spanish SII requirements for VAT reporting (Immediate Information Supply).  

## Enable the SII module in the Spanish version of Business Central

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SII Setup**, and then select the related link.  
2. On the **General** FastTab, select the **Enabled** field.  

   The **Enabled** field is automatically selected if you import a certificate in the **Certificate Code** field on the **Certificate** FastTab.  

3. In the **Operation Date** field, specify whether you want to use the posting date or the document date as the operation date in the XML file that's sent to the tax authorities through SII.  
4. If you want to submit documents in batches, select the **Enable Batch Submission** field. If you enable document batch submissions, you can submit documents in batches either manually or automatically. For automatic batch submission, documents are transferred to the **SII History** page in a status of *Pending* when you post them. Then, when the threshold value is met or exceeded, the documents are submitted in batches. Learn more in the [Job batch submission thresholds](#job-batch-submission-thresholds) section.

   If you don't enable batch submissions, each document is submitted when it's posted, and the result is shown on the **SII History** page.
   
5. Configure the other fields, import a valid certificate, and specify the relevant endpoints with the target URLs. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
6. Choose the **Tax Period** option for reporting. Default value is **Monthly**, but user can choose **Quarterly** if needed. If user use **Quarterly** it will be showed in the XML message.  

## Job batch submission thresholds

If you want to use automatic batch submission, the **Job Batch Submission Threshold** field specifies the threshold number of documents with the status *Pending* that will trigger an automatic batch submission.

> [!IMPORTANT]
> Both the **Enabled** and the **Enabled Batch submission** fields must be selected for the threshold value to have effect.  

If the threshold is set to zero (0), documents will be submitted when posted.

If the threshold is set to one or more, documents are automatically submitted in batches. When the number of pending entries exceeds the threshold value, all pending entries are automatically submitted.  

You can always manually submit documents that have a *Pending* status by selecting **Retry** or **Retry All** on the **SII History** page.

## Specify customers without a registered NIF with AEAT

If a customer's NIF number isn't yet registered in the AEAT database, document submissions will be rejected. In this case, you can select the **Not in AEAT** option and resubmit the document.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. Choose the relevant customer to open the **Customer Card**.
3. Select the **Not in AEAT** field.

## Set VAT exemptions

To indicate value-added tax (VAT) exemptions under the SII scheme you can either select an exemption code for a VAT clause on the **VAT Clauses** page, or you can create a new clause that corresponds to the exemption and choose the appropriate code in the **SII Exemption Code** field.

>[!IMPORTANT]
>The default values are provided to cover standard scenarios. Your business and type of business transactions and any customization you may have may require you to select a different value to meet the reporting requirements under SII.

To enable reporting on **Non Taxable Due To Localization Rules** scenarios, set the appropriate **VAT Posting Setup Card** on the **VAT Posting Setup** page by selecting the option in the **No Taxable Type** field. To ensure that **VAT Posting Setup** works this way, the value of the **VAT %** field must equal **0** (zero). 

When you post the document, and the VAT is configured with the active **No Taxable Type** field, this field together with the **VAT Entry** field will create a new **No Taxable Entry** that has details about this tax exemption.

### VAT reporting based on VAT exemption

The **Calc. and Post VAT Settlement** report processes the **No Taxable Entries** in a similar way to **VAT Entries**. You can post some documents with **No Taxable** selected for a specific period for three different no taxable **VAT Posting Setup** entries and run the **The Calc. and Post VAT Settlement** report. The **No Taxable** section will be printed below the **VAT Entries** section on the report.

If you decide to close some entries for **VAT Posting Setup**, the system automatically closes the **No Taxable Entries** that are connected with this **VAT Entry**. If you run the **Calc. and Post VAT Settlement** report, it shows all other entries but doesn't include closed entries for the same period.

> [!NOTE]
> You can generate the **VAT Declaration** on the **VAT Statements** page. Select **Preview** on the **VAT Statements** page to view the result for the option **Include VAT Entries** = **Open**. This option also works for **No Taxable Entries**. Printing of the **VAT Statement** report also supports the **Include VAT Entries** option for the same values (**Open**, **Closed**, and **Open and Closed**) for both **VAT Entries** and **No Taxable Entries**.

## Ignoring invoice lines for SII 

In some situations, the user must use a line in the invoice, but not report it to SII. To make a setup for this requirement, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then select the related link. 
1. Open the **VAT Posting Setup Card** where you want to configure this exemption and choose the **Ignore in SII** field for this posting group.  

When you have configured **VAT Posting Setup**, and after you create sales or purchase invoice, you can select **Item** and/or **G/L Account** with the certain **VAT Posting Setup**, and the line with this setup will be ignored when you report it to SII. This line exists in the **VAT Entry**, but this entry will have *Yes* in the **Ignore in SII** field.  

## Related information

[SII - Invoice and Credit Memo Types in Sales and Purchase Documents](SII-invoice-types-sales-purchase-documents.md)    
[Spain Local Functionality](spain-local-functionality.md)    

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
