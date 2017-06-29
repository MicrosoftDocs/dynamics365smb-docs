---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Set Up and Record Intrastat
All companies in the European Union must report their trade with other EU countries\/regions. You must report the movement of goods to the statistics authorities in your country\/region every month, and the report must be delivered to the tax authorities. This is referred to as Intrastat Reporting. You use the **Intrastat Journal** window to complete periodic Intrastat reports.  
  
### To set up Intrastat  
  
1.  In the **Search** box, enter **Tariff Numbers**, and then choose the related link.  
  
2.  In the **Tariff Numbers** window, enter the published tariff numbers for all items that you buy and sell. FIX INCLUDE HERE<!--[!INCLUDE[bp_fieldhelp]()] -->  
  
3.  In the **Search** box, enter **Transaction Types**, and then choose the related link.  
  
4.  In the **Transaction Types** window, enter the 22 pre\-defined Intrastat transaction types and codes.  
  
5.  In the **Search** box, enter **Transport Methods**, and then choose the related link.  
  
6.  In the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Transport Methods** window, enter the seven pre\-defined Intrastat transport methods and codes.  
  
     You must fill in the above tables and assign **Transaction Types** and **Transport Method** values on the **Foreign Trade** FastTab of each sales and purchase document before you post any sales or purchases in FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> -->.  
  
7.  In the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Item Card** window, on the **Foreign Trade** FastTab, enter the appropriate Tariff number for this item in the **Tariff No.** field.  
  
 Repeat the steps for all items. Tariff numbers must be assigned to each item.  
  
 In order for item entries to contain the necessary information when [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] imports them to the Intrastat journal line, you must have entered the necessary information.  
  
##### Additional setup  
  
-   You can set up **Transaction Specifications** and **Areas** to supplement the transaction type information and country\/region information. **Transaction Specifications** and **Areas** are also assigned to sales and purchase document on the **Foreign Trade** FastTab.  
  
-   **Entry\/Exit Points** can be created for the location to which items from abroad are shipped or from which you ship items abroad. Heathrow Airport is an example of an Entry\/Exit Point. **Entry\/Exit Points** can be entered on sales and purchase documents on the **Foreign Trade** FastTab. This information will also be copied from the item entries when you create the Intrastat journal.  
  
## To set up Intrastat journals  
 Before you can use the **Intrastat Journal** window, you must setup Intrastat journal templates and batches.  
  
#### To fill in the Intrastat journal  
  
-   You can fill in the Intrastat Journal with the relevant item ledger entries using the Get Entries function, or manually. If you have relevant general ledger entries in addition to the item ledger entries, you make these manually. Such manual adjustments could include service charges, freight costs, landed costs, and so on.  
  
 The **Intrastat Jnl. Line** window must be used for Intrastat reporting. All EU businesses must report their trade with other EU countries\/regions.  
  
### To submit Intrastat  
  
-   After you have filled in the Intrastat Journal, you can print the **Intrastat \- Checklist** report to make sure that that all information in the journal is correct, and then print an intrastat report onto a form or create one on a disk to submit to the tax authority in your country\/region.  
  
## See Also  
 [How to: Record VAT](../Finance/how-to-record-vat.md)   
 [How to: Reorganize Intrastat Journals](../Finance/how-to-reorganize-intrastat-journals.md)   
 [How to: Set Up Intrastat Journal Templates and Batches](../Finance/how-to-set-up-intrastat-journal-templates-and-batches.md)   
 [How to: Fill In Intrastat Journals](../Finance/how-to-fill-in-intrastat-journals.md)   
 Intrastat Jnl. Line   
 Intrastat \- Checklist   
 [How to: Report Intrastat on Forms](../Finance/how-to-report-intrastat-on-forms.md)   
 [How to: Report Intrastat on a Disk](../Finance/how-to-report-intrastat-on-a-disk.md)