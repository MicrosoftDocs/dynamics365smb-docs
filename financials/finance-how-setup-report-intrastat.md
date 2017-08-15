---
title: Set Up and Report Intrastat| Microsoft Docs
description: Learn how to set up Intrastat reporting features, and how to report trade with companies in other EU countries.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union 
ms.date: 08/15/2017
ms.author: bholtorf

---
# How To: Set Up and Record Intrastat
All companies in the European Union must report their trade with other EU countries/regions. You must report the movement of goods to the statistics authorities in your country/region every month, and the report must be delivered to the tax authorities. This is referred to as Intrastat Reporting. You use the **Intrastat Journal** page to complete periodic Intrastat reports.

Before you can use the Intrastat journal, there are several things to set up:

* **Intrastat journal templates**: You must set up the Intrastat journal templates and batches you will use. Because Intrastat is reported monthly, you must create 12 Intrastat journals based on the same template. 
* **Commodity codes**: Customs and tax authorities have established eight-digit codes for different types of items. You specify these codes on items as commodity codes.
* **Transaction types**: Countries and regions have different codes for types of Intrastat transactions, such as ordinary purchase and sale, exchange of returned goods, and exchange of non-returned goods. Set up all of the codes that apply to your country/region. You specify transaction types on sales and purchase documents.  <!-- Don't see a Transaction Types page. Are these "transaction specifications?"  -->
* **Transport methods**: There are seven, one-digit codes for Intrastat transport methods. **1** for sea, **2** for rail, **3** for road, **4** for air, **5** for post, **7** for fixed installations, and **9** for own propulsion (for eample, transporting a car by driving it). Financials does not require these codes, however, we recommend that the descriptions provide a similar meaning.  

Optionally, you can also specify:

* **Transaction specifications**: Use these to supplement the descriptions from the transaction types. <!-- Can we give an example of the additional information? -->
* **Areas**: Use these to supplement information about countries and regions. <!-- Can we give an example of the additional information? -->
* **Entry/exit points**: Use these to specify the locations where you ship or receive items to or from other countries. Heathrow Airport is an example of an entry or exit point. You enter entry or exit points on sales and purchase documents on the **Foreign Trade** FastTab. This information will also be copied from the item entries when you create the Intrastat journal.

## To set up Intrastat templates and batch jobs
The Intrastat batch jobs include only item entries, and not general ledger entries. If you have general ledger entries that qualify for Intrastat reporting, you must enter them manually. For example, if you purchase a computer from another EU country or region, the computer is not placed in inventory, but is posted to a general ledger account. You must manually enter this type of entry in the Intrastat journal.  
  
You can export the entries to a file that you can send to your Intrastat authorities. You can also print a report, manually enter the information on the forms from your authorities, and then submit the information.

>  [!Note]
> We recommended that you set up an Intrastat journal batch for each month. Also, note that Intrastat journal batches are not similar in structure to other journal batches. <!-- What's the diff, and why is it important to mention? -->

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journal Templates**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Create a template for each Intrastat form you use. <!-- how many forms are there, or should this be, "Create a template for the Intrastat form for your country/region"?-->
3. On the **Navigate** tab, choose **Batches**.
4. On each batch line, fill in the fields described in the following table.

|Field | Description|
|---|---|
|**Statistics Period** | Enter the statistics period as a four-digit number, where the first two digits represent the year and the next two digits represent the month. For example, enter 1706 for June 2017.|
|**Currency Identifier** | Enter a code that identifies the currency of the Intrastat report. For example, you can enter EUR for euro and USD for US dollars.|
|**Amounts in Add. Currency** | Select this field if you want the Intrastat report to display in the additional reporting currency.|
|**Reported** | This field is automatically filled in when you run the Intrastat - Make Disk Tax Auth batch job. If you want to run the batch job again, clear this field.|

<!-- I don't see the Intrastat - Make Disk Tax Auth batch job described anywhere-->

## To assign commodity codes to items
All items that you buy or sell must have a commodity code. To assign a commodity code to an item, on the **Item Card** page, expand the **Foreign Trade** FastTab, and then enter the code in the **Commodity Code** field.

## To set up transaction specifications
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transaction Specifications**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To set up transport methods
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transport Methods**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Additional setups
You can set up transaction specifications and areas to supplement the transaction type information and country/region information. When you create sales and purchase documents, you assign transaction specifications and areas on the **Foreign Trade** FastTab.
Additionally, you can create entry and exit points for the locations where you ship items to, or receive items from, other countries. 

## To submit Intrastat
After you have filled in the Intrastat Journal, you can print the **Intrastat - Checklist** report to make sure that that all information in the journal is correct, and then print an Intrastat report onto a form or create one on a disk to submit to the tax authority in your country/region.

### To fill in Intrastat journals  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journal** and then choose the related link.  
2. In the **Intrastat Journal** window, in the **Batch Name** field, select the relevant journal batch, and then choose the **OK** button.  
3. On the **Actions** tab, choose **Get Entries**. The **Starting Date** and **Ending Date** fields will already contain the dates specified for the statistics period on the journal batch.  
4. In the **Cost Regulation %** field, you can enter a percentage to cover transport and insurance. If you enter a percentage, the content of the **Statistical Value** field in the journal is proportionally higher.  
5. Choose **OK** to start the batch job.  
  
The batch job retrieves all the item entries in the statistics period and inserts them as lines in the Intrastat journal. You can edit the lines if needed.  
  
> [!IMPORTANT]  
>  The batch job retrieves only the entries that contain a country/region code for which an Intrastat code has been entered on the **Countries/Regions** page. Therefore, you must enter Intrastat codes for the country/region codes for which you will run the batch job.  

### How to: Report Intrastat on Forms
To get the information that is required on the Intrastat form from the statistical authorities, you must print the **Intrastat – Form** report. Before you can do this, you must prepare the Intrastat journal and fill it in. If you have both sales and purchase transactions, you must complete a separate form for each type, so that you must print the report two times.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journals**, and then choose the related link.  
2. On the **Intrastat Journal** page, choose the relevant journal batch in the **Batch Name** field.  
3. If you have not already done this, fill in the journal manually or on the **Actions** tab, choose **Get Entries**.  
4. On the **Actions** tab, choose **Form**.  
5. On the **Intrastat Jnl. Line** FastTab, add a **Type** filter and then specify whether this is a **Receipt** or a **Shipment**.  
6. Choose **Print** to print the report.  

### How to: Report Intrastat on a Disk
You can submit the Intrastat report on a disk. Before creating the file, you can print a checklist that contains the same information that will be in the file.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journal**, and then choose the related link.  
2. In the **Intrastat Journal** window, select the relevant journal batch in the **Batch Name** field.  
3. If you have not already done this, fill in the journal manually or on the **Home** tab, in the **Process** group, choose **Get Entries**.  
4. On the **Home** tab, choose **Make Diskette**.  
5. In the batch job window, choose **OK**.  
6. Choose **Save**.  
7. Browse to the location where you want to save the file, enter the file name, and then choose **Save**. 

## How to: Reorganize Intrastat Journals
Because you must submit an Intrastat report every month, and you create a new journal batch for each report, you will eventually have many journal batches. The journal lines are not deleted automatically. You may want to reorganize the journal batch names periodically. You do this by deleting the journal batches that you no longer need. The journal lines in these batches are also deleted.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journals**, and then choose the related link.  
2. To view the options, choose the **Batch Name** field.  
3. Choose the journal batches to deleted, and then choose **Delete**.  