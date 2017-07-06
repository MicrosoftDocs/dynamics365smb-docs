---
    title: How to: Fill In Intrastat Journals | Microsoft Docs
    description: You can fill in the fields in the Intrastat journal manually or retrieve item entries automatically with a batch job. Before you can do this, you must set up the Intrastat journal templates and batches.
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
>  The batch job retrieves only the entries that contain a country/region code for which an Intrastat code has been entered in the **Countries/Regions** window. Therefore, you must enter Intrastat codes for the country/region codes for which you will run the batch job.  
  
## See Also  
 [How to: Create a VAT Combination Setup](../how-to-create-a-vat-combination-setup.md)   
 [How to: Report Intrastat on a Disk](../how-to-report-intrastat-on-a-disk.md)   
 [How to: Report Intrastat on Forms](../how-to-report-intrastat-on-forms.md)   
 [How to: Reorganize Intrastat Journals](../how-to-reorganize-intrastat-journals.md)