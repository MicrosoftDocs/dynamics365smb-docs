---
title: Set up and report Intrastat
description: Learn how to set up Intrastat reporting features, and how to report trade with companies in other EU countries/regions.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.search.form: 308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 8451, 12202, 31077
ms.date: 08/26/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set up and report Intrastat

All companies in the European Union must report their trade with other EU countries/regions. You must report the movement of goods to the statistics authorities in your country/region every month, and the report must be delivered to the tax authorities. This is referred to as Intrastat Reporting. You use the **Intrastat Journal** page to complete periodic Intrastat reports.

[!INCLUDE[intrastat-2022w2](includes/intrastat-2022w2.md)]

## Required and optional Setups

> [!IMPORTANT]
> Customer cards and Vendor cards include a field, **Intrastat Partner Type**, that has the same option values as the **Partner Type** field: *"" (blank)*, *Company*, and *Person*. The **Intrastat Partner Type** field has replaced the **Partner Type** field in Intrastat reporting. **Partner Type** is used in SEPA to define the SEPA Direct Debit Scheme (Core or B2B). **Intrastat Partner Type** is used for Intrastat reporting only. This way, you can specify different values for the two fields, if you need to.
>
> However, note that if the **Intrastat Partner Type** field is left blank, the value from the **Partner Type** field is used for Intrastat reporting.

Before you can use the Intrastat journal to report Intrastat information, there are several things you must set up:  

* **Intrastat Setup**: Intrastat Setup page is used to enable intrastat reporting and set defaults for it. You can specify whether you need to report Intrastat from shipments (dispatches), receipts (arrivals) or both depending on thresholds set by your local regulations. You can also set default transaction types for regular and return documents, used for nature of transaction reporting.
* **Intrastat journal templates**: You must set up the Intrastat journal templates and batches you will use. Because Intrastat is reported monthly, you must create 12 Intrastat journal batches based on the same template.  
* **Commodity codes**: Customs and tax authorities have established numerical codes that classify items and services. You specify these codes on items.
* **Transaction nature codes**: Countries and regions have different codes for types of Intrastat transactions, such as ordinary purchase and sale, exchange of returned goods, and exchange of non-returned goods. Set up all of the codes that apply to your country/region. You use these codes on the **Foreign Trade** FastTab on sales and purchase documents, and when you process returns.

    > [!NOTE]
    > Starting in January 2022, Intrastat requires different transaction nature code for dispatches to private individuals or non-VAT registered businesses and VAT registered businesses. To comply with this requirement, we recommend that you review and/or add new transaction nature codes in the **Transaction Types** page according to the requirements in your country. You should also review and update the **Intrastat Partner Type** field to *Person* for private individual or non-VAT registered businesses customers in the relevant **Customer** page. If you are unsure about the correct intrastat partner type or transaction type to use, we recommend that you ask an expert in your country or region.

* **Transport methods**: There are seven, one-digit codes for Intrastat transport methods. **1** for sea, **2** for rail, **3** for road, **4** for air, **5** for post, **7** for fixed installations, and **9** for own propulsion (for example, transporting a car by driving it). [!INCLUDE[prod_short](includes/prod_short.md)] does not require these codes, however, we recommend that the descriptions provide a similar meaning.  
* **Transaction specifications**: Use these to supplement the descriptions from the transaction types.  
* **Country of origin**: Use the two-letter ISO Alpha Codes for the country/region where the good was obtained or produced. If the good was produced in more than one country/region, the country/region of origin is the last country where it was significantly processed.
* **VAT identification number of the partner operator in the Member State of import**: This is the VAT-ID number of the partner operator in the Member State of import. The VAT-ID is also used in the exchange of intra-EU-export data among Member States, and allows Member States to allocate the received data to the importing company in their own country/region. Reporting units must report the VAT-ID of the company that declared the intra-Union acquisition of goods in the Member State of import.

> [!NOTE]
> The business partner VAT-ID to use can differ, depending on the business circumstance. For example, the ID to use differs for scenarios such as chain sales, where a supplier sells a product to another country, and then that company resells the item to another business in the same country, triangular trade, and so on. If you are unsure about the correct VAT-ID to use, we recommend that you ask an expert in your country or region.

Optionally, you can also set up:

* **Areas**: Use these to supplement information about countries and regions.  
* **Entry/exit points**: Use these to specify the locations where you ship or receive items to or from other countries/regions. Heathrow Airport is an example of an entry or exit point. You enter entry or exit points on sales and purchase documents on the **Foreign Trade** FastTab. This information will also be copied from the item entries when you create the Intrastat journal.  

### To set up Intrastat templates and batches

The Intrastat batch jobs include only item entries, and not general ledger entries. If you have general ledger entries that qualify for Intrastat reporting, you must enter them manually. For example, if you purchase a computer from another EU country or region, the computer is not placed in inventory, but is posted to a general ledger account. You must manually enter this type of entry in the Intrastat journal.  

You can export the entries to a file that you can send to your Intrastat authorities. You can also print a report, manually enter the information on the forms from your authorities, and then submit the information.

> [!NOTE]
> We recommended that you set up an Intrastat journal batch for each month.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal Templates**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Create a template for each Intrastat form you use.  
3. To create batches, choose the **Batches** action.  
4. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Create a template for each Intrastat form you use.

> [!NOTE]
> In the **Statistics Period** field, enter the statistics period as a four-digit number, where the first two digits represent the year and the next two digits represent the month. For example, enter 1706 for June, 2017.

### To set up transport methods

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transport Methods**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### To set up which Intrastat report fields are mandatory

In some countries/regions, such as Spain and UK, the authorities require that Intrastat reports include, for example, the shipment method for purchases or some other values when sales are over a certain threshold. On the **Intrastat Setup** page, you can select to make **Intrastat Checklist Setup** to set mandatory fields on the **Intrastat Journal** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Setup**, and then choose the related link.
2. Choose the **Intrastat Checklist Setup** action.
3. On the **Intrastat Checklist Setup** page, select in the **Field Name** to pick Intrastat report field you want to make mandatory.

### Czechia

Specifically for Czech businesses, you must also set up commodity codes and transaction nature codes.  

#### To set up commodity codes

All items that you buy or sell must have a commodity code.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Commodity Codes**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. To assign a commodity code to an item, go to the **Item Card** page, expand the **Costs & Posting** FastTab, and then enter the code in the **Commodity Code** field.

### Italy

Specifically for Italian businesses, you must also set up commodity codes and transaction nature codes.  

#### To set up transaction nature codes

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transaction Nature Codes**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

> [!TIP]
> If you frequently use a particular transaction nature code, you can make it the default. To do this, go to the **Intrastat Setup** page, and choose the code.

## To report Intrastat

After you fill in the Intrastat journal, you can run the **Checklist report** action to make sure that all information in the journal is correct. Mandatory fields you have set in **Intrastat Checklist Setup** page that are missing values will be shown in Errors and warning fact box on the **Intrastat Journal** page. Afterward, you can print an Intrastat report as a form, or create a file to submit to the tax authority in your country/region.  

### To fill in Intrastat journals

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal** and then choose the related link.  
2. On the **Intrastat Journal** page, in the **Batch Name** field, choose the relevant journal batch, and then choose **OK**.  
3. Choose the **Suggest Lines** action. The **Starting Date** and **Ending Date** fields will already contain the dates specified for the statistics period on the journal batch.  
4. In the **Cost Regulation %** field, you can enter a percentage to cover transport and insurance. If you enter a percentage, the content of the **Statistical Value** field in the journal is proportionally higher.  
5. Choose **OK** to start the batch job.  

The batch job retrieves all the item entries in the statistics period and inserts them as lines in the Intrastat journal. You can edit the lines if needed.  

> [!IMPORTANT]  
> The batch job retrieves only the entries that contain a country/region code for which an Intrastat code has been entered on the **Countries/Regions** page. Therefore, you must enter Intrastat codes for the country/region codes for which you will run the batch job. The batch job sets the **Partner VAT ID** field to *QV999999999999* for private individuals or non-VAT registered businesses (customers with the **Intrastat Partner Type** field set to *Person*), and it uses the value of the **Transaction Type** field on the posted item ledger entry or job ledger entry.

### To modify Intrastat journals lines

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal**, and then choose the related link.  
2. On the **Intrastat Journal** page, in the **Batch Name** field, choose the relevant journal batch, and then choose **OK**.  
3. User filter pane to filter Intrastat Journal lines based on some criteria. For example, filter on **Partner VAT ID** fields with the value *QV999999999999*.
4. Choose **Share** icon ![Share a page in another app.](media/share-icon.png) and select **Edit in Excel**
5. In Excel, modify the Intrastat journal lines that you filtered out. For example, modify **Transaction Type** field values.  
6. Publish the changes that you have made in Excel back to [!INCLUDE[prod_short](includes/prod_short.md)]

> [!NOTE]
> In [!INCLUDE[prod_short](includes/prod_short.md)] versions that do not support [**Edit in Excel**](across-work-with-excel.md#edit-in-excel) for journals, you can create configuration packages to export and import Intrastat journal lines to Excel. For more information, see [Migrate On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) in the administration content.

### Report Intrastat on a form or a file

To get the information that is required on the Intrastat form from the statistical authorities, you must print the **Intrastat – Form** report. Before you can do this, you must prepare the Intrastat journal and fill it in. If you have both sales and purchase transactions, you must complete a separate form for each type, so that you must print the report two times.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.  
2. On the **Intrastat Journal** page, choose the relevant journal batch in the **Batch Name** field.  
3. If you have not already done this, fill in the journal manually or choose **Suggest Lines** action.  
4. Choose the **Prints Intrastat Journal** action.  
5. On the **Intrastat Jnl. Line** FastTab, add a **Type** filter and then specify whether this is a **Receipt** or a **Shipment**.  
6. Choose **Send to** to print the report.  

### Report Intrastat in a file

You can submit the Intrastat report as a file. Before creating the file, you can print a checklist that contains the same information that will be in the file.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal**, and then choose the related link.  
2. On the **Intrastat Journal** page, select the relevant journal batch in the **Batch Name** field.  
3. If you have not already done this, fill in the journal manually or by choosing the **Suggest Lines** action.  
4. Choose the **Create File** action.  
5. On the batch job page, choose the **OK** button.  
6. Choose **Save**.  
7. Browse to the location where you want to save the file, enter the file name, and then choose **Save**.

> [!NOTE]
> When a line in the Intrastat report has a supplementary unit of measure, the weight of the item will not be shown, since this value is not required.

## Reorganize Intrastat journals

Because you must submit an Intrastat report every month, and you create a new journal batch for each report, you will eventually have many journal batches. The journal lines are not deleted automatically. You may want to reorganize the journal batch names periodically. You do this by deleting the journal batches that you no longer need. The journal lines in these batches are also deleted.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.  
2. To view the options, choose the **Batch Name** field.  
3. Choose the journal batches to be deleted, and then choose the **Delete** button.  

## Tariff numbers

In many countries/regions, the customs and tax authorities establish 8-digit item codes for various items. In order for item entries to contain the necessary information when the program imports them to the Intrastat journal line, you must have entered the information about the tariff number in the **Tariff Numbers** page. Find the codes for the items that your company deals with and enter them in the **Tariff Numbers** page.

In the **Tariff Numbers** page, add all the codes that you use. You must enter the codes on the item card before you begin to post. When you have set up the codes, enter them in the **Tariff No.** field on the item card. You must also fill in the **Net Weight** field on the item card.

## Related information

[Financial Management](finance.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
