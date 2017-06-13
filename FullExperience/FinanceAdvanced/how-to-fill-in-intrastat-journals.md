---
title: "How to: Fill In Intrastat Journals"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Intrastat, journals"
  - "Intrastat, filling in journals"
ms.assetid: 92248e55-8a6c-45c7-be9b-e9af8ee146fb
caps.latest.revision: 6
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Fill In Intrastat Journals
You can fill in the fields in the Intrastat journal manually or retrieve item entries automatically with a batch job. Before you can do this, you must set up the Intrastat journal templates and batches.  
  
### To fill in Intrastat journals  
  
1.  In the **Search** box, enter **Intrastat Journal** and then choose the related link.  
  
2.  In the **Intrastat Journal** window, in the **Batch Name** field, select the relevant journal batch, and then choose the **OK** button.  
  
3.  On the **Actions** tab, in the **Process** group, choose **Get Entries**. The **Starting Date** and **Ending Date** fields will already contain the dates specified for the statistics period on the journal batch.  
  
4.  In the **Cost Regulation %** field, you can enter a percentage to cover transport and insurance. If you enter a percentage, the content of the **Statistical Value** field in the journal is proportionally higher.  
  
5.  Choose the **OK** button to start the batch job.  
  
 The batch job retrieves all the item entries in the statistics period and inserts them as lines in the Intrastat journal. If any information is missing, you can enter it in the relevant fields.  
  
> [!IMPORTANT]  
>  The batch job retrieves only the entries that contain a country\/region code for which an Intrastat code has been entered in the **Countries\/Regions** window. Therefore, you must enter Intrastat codes for the country\/region codes for which you will run the batch job.  
  
## See Also  
 [How to: Create a VAT Combination Setup](../Finance/how-to-create-a-vat-combination-setup.md)   
 [How to: Report Intrastat on a Disk](../Finance/how-to-report-intrastat-on-a-disk.md)   
 [How to: Report Intrastat on Forms](../Finance/how-to-report-intrastat-on-forms.md)   
 [How to: Reorganize Intrastat Journals](../Finance/how-to-reorganize-intrastat-journals.md)