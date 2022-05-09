---
    title: SII Setup and Invoice Types in Sales and Purchase Documents
    description: Shows the basic SII setup and output of the various types that are used for invoices and credit memos in connection with SII and how they are implemented.

    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.search.form: 10751, 10752, 10753, 10770, 10771
    ms.date: 04/01/2021
    ms.author: edupont

---
# SII Setup
To enabble the SII module in Spanish version:
1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SII Setup**, and then choose the related link.  
2.  In the **General** FastTab, change to YES field **Enabled**. **Enabled** field is automatically enabled if you import certificate in field **Certificate Code** in the **Certificat** FastTab.
3.  In the **Operation Date** field the user can choose between Posting Date or Document Date, to be used as *Operation Date* in the XML sent via SII to the Tax Authorities.
4.  If you want to submit documents in batches you need to enable the  **Enable Batch Submission** field and to choose how you want to submit them in the **Job Batch Submission Threshold** field, where you can specifiy the minimal number of pending history records for the batch submission.
    > [!NOTE]  
    > You can use enabling batch submissions of documents as the following:
    > - When you enable batch submissions you can either manually submit document in batches or automatically.
    > - Not enabled: each document is submitted when you post the document, and the result is shown in the **SII History** page.
    > - Automatically: Documents are transferred to **SII History** with **Status** = Pending when you post them and submitted in batches when threshold value is met or exceeded, see info on **Job Batch Submission Threshold** below.

    > [!NOTE]  
    > If you want to use **Job Batch Submission Threshold** you shoul now the following:
    > - Specify the threshold number of documents with status = Pending that will trigger an automatic batch submission.
    > - **Enabled** and **Enabled Batch submission** must both be set to Yes for the threshold value to have effect.
    > -- If Threshold = 0, documents will be submitted in *single* submission mode, which means that they will be submitted when you post the document.
    > -- If Threshold > 0 it is used for batch submission. If number of pending entries exceeds the threshold value the system submits ALL pending auto entries.
    > -- User can always manually submit documents while they are Status = Pending (Retry, Retry All).
5. Configure other fields, import valid certificate, and configure endpoints with targeted URLs.

# SII - Invoice and Credit Memo Types in Sales and Purchase Documents

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the Spanish SII requirements for VAT reporting (Immediate Information Supply).  

The following table shows the output of the various types that are used for invoices and credit memos in connection with SII and how they are implemented in [!INCLUDE[prod_short](../../includes/prod_short.md)].

## Sales Invoices
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice|
|F2|Simplified invoice (ticket)|Implemented as for F1, except a non-existing block is called "Contraparte" and additional nodes are called "ImporteTotal" and "Macrodato".|
|F3|Invoice issued to replace simplified invoices issued and filed|Same as Normal invoice|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[prod_short](../../includes/prod_short.md)] does not support Summary invoices. <br /><br />Submissions will result in known error: Missing "NumSerieFacturaEmisorResumenFin" element.|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Not supported. Only used for credit memos.|
|R2|Corrected invoice (Art. 80.3)|Not supported. Only used for credit memos|
|R3|Corrected invoice (Art. 80.4)|Not supported. Only used for credit memos|
|R4|Corrected invoice (other)|Not supported. Only used for credit memos|
|R5|Corrected invoice in simplified invoices|Not supported. Only used for credit memos|

## Sales Credit Memos
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Same structure as sales invoice, type F1, but with negative values|
|F2|Simplified invoice (ticket)|Same structure as sales invoice type F2, but with negative values|
|F3|Invoice issued to replace simplified invoices issued and filed|Not supported|
|F4|Invoice summary entry|Not supported|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Normal credit memo|
|R2|Corrected invoice (Art. 80.3)|Same as normal credit memo|
|R3|Corrected invoice (Art. 80.4)|Same as normal credit memo|
|R4|Corrected invoice (other)|Same as normal credit memo|
|R5|Corrected invoice in simplified invoices|Same as normal credit memo except the block is called "Contraparte".|

## Purchase Invoices
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice|
|F2|Simplified invoice (ticket)|Implemented as for F1, except a non-existing block is called "Contraparte" and additional nodes are called "ImporteTotal" and "Macrodato".|
|F3|Invoice issued to replace simplified invoices issued and filed|Sames as for Normal invoice|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[prod_short](../../includes/prod_short.md)] does not support Summary invoices. <br /><br />Submissions will result in known error: Missing "NumSerieFacturaEmisorResumenFin" element.|
|F5|Imports (DUA)|Same as for Normal invoice|
|F6|Accounting support material|Sames as for Normal invoice|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Not supported. Only used for credit memos|
|R2|Corrected invoice (Art. 80.3)|Not supported. Only used for credit memos|
|R3|Corrected invoice (Art. 80.4)|Not supported. Only used for credit memos|
|R4|Corrected invoice (other)|Not supported. Only used for credit memos|
|R5|Corrected invoice in simplified invoices|Not supported. Only used for credit memos|

## Purchase Credit Memos
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Same structure as for purchase invoice, type F1, but with negative values|
|F2|Simplified invoice (ticket)|Same structure as for purchase invoice, type F1, but with negative values|
|F3|Invoice issued to replace simplified invoices issued and filed|Not possible|
|F4|Invoice summary entry|Not possible|
|F5|Imports (DUA)|Not possible|
|F6|Accounting support material|Not possible|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Normal credit memo|
|R2|Corrected invoice (Art. 80.3)|Same as normal credit memo|
|R3|Corrected invoice (Art. 80.4)|Same as normal credit memo|
|R4|Corrected invoice (other)|Same as normal credit memo|
|R5|Corrected invoice in simplified invoices|Same as for normal credit memo except the block is called "Contraparte"|

## See Also

[Spain Local Functionality](spain-local-functionality.md)
[Setup and user guide for electronic VAT information under SII in the Spanish version of Dynamics NAV](https://aka.ms/SIISetup)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
