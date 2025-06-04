---
title: Work with Intrastat reporting
description: Learn how to report trade with companies in other EU countries/regions using the Intrastat system.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.search.form: 308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 4810, 4811, 8451, 12202, 31077
ms.date: 08/26/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Work with Intrastat reporting

All companies in the European Union (EU) must report their trade with other EU countries/regions. You must report the movement of goods to the statistics authorities in your country/region every month, and the report must be delivered to the tax authorities. Intrastat is the system for collecting trade statistics of goods within these countries/regions. You use **Intrastat Report** to complete periodic Intrastat reporting (typically monthly), collecting, recording, and reporting trade of goods as per local government legislation.

Intrastat reporting is based on basic EU regulations that apply to all countries/regions; however, in practice, there are some differences within the individual countries/regions. Each country/region has its rules of what exactly and how to report.

> [!IMPORTANT]  
> This article describes the new Intrastat experience available in [!INCLUDE[prod_short](includes/prod_short.md)] starting in the 2022 release wave 2, which includes extended features, but if you didn't upgrade your solution, read the previous version's Intrastat setup and usage article at [Set Up and Report Intrastat](finance-how-setup-report-intrastat-v20.md).

> [!NOTE]  
> Intrastat information doesn't apply to the movement of services between countries/regions, but only goods (Items and Fixed Assets). If the local government requires registering  the movement of services between countries/regions, it can be done using the **Service Declaration** feature.
>
> This features is available as an app at [AppSource](https://go.microsoft.com/fwlink/?linkid=2081646). At that time, to use it, you must first install it on the **Extension Management** page. Learn more about this functionality [here](finance-how-setup-use-service-declaration.md).  

## Fill in the Intrastat report

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report List**, and choose the related link.
2. Choose **New** action to create a new **Intrastat Report**.
3. If you need to enter some internal information about the **Intrastat Report**, fill in this information in the **Description** field.
4. In the **Statistic Period** field, specify the month to report data for. Enter the period as a four-digit number with no spaces or symbols. Depending on your country/region, enter either the month first and then the year, or vice versa. For example, enter either *2206* or *0622* for June 2022.
5. Choose the **Suggest Lines** action. The **Starting Date** and **Ending Date** fields will already contain the dates specified for the statistics period on the Intrastat report header.
6. In the **Cost Regulation %** field, you can enter a percentage to cover transport and insurance. If you enter a percentage, the content of the **Statistical Value** field in the journal is proportionally higher. But if you want to use this feature, you must switch the **Amount incl. Item Charges** field to **Yes**.
7. You can eventually set up extra configurations on the **Additional** FastTab:
   1. **Skip Recalculation for Zero Amounts** to specify that lines without amounts won't be recalculated during the batch job.
   2. **Skip Zero Amounts** to specify that item ledger entries without amounts won't be included in the batch job.
   3. **Skip Non-Invoiced Entries** to specify if item ledger entries that are shipped or received but not yet invoiced must be excluded from the process.
8. Choose **OK** to start the batch job.

The batch job retrieves all the item entries in the statistics period and inserts them as lines in the **Intrastat Report** lines. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Modify the Intrastat report

If needed, you can modify the lines, but whenever you change a value in the Intrastat report line, the **Correction** field will be automatically marked as **Yes**. Eventually, you can add a new line manually if there's a reason for that. To add a new line manually:

1. On the **Intrastat Report** page, choose the **New Line** action in the **Lines** FastTab.
2. Choose the **Receipt** or **Shipment** option in the **Type** field.
3. In the **Source Type** field, choose one of the sources: **Item Entry**, **FA Entry**, or **Job Entry**.
4. Based on the **Source Type** in the **Item No.** field, you can choose an **Item** (in both cases, **Item Entry** or **Job Entry**) or **Fixed Assets**.
5. Fill in other fields as you need for the Intrastat reporting.

> [!NOTE]  
> When you manually add a new line to the Intrastat report, the **Date** field in the line must be inside the **Statistic Period** range you added on the header.

## Validate Intrastat lines

After you fill in the **Intrastat Report**, you can run the **Checklist Report** action to ensure that all information in the **Intrastat Report** is correct. Mandatory fields you have set on Intrastat Report Checklist page that is missing values will be shown in **Errors and warning** FactBox on the **Intrastat Report** page.

Run the **Intrastat Report Checklist** report to check Intrastat lines before they're exported to the required format. The check is run inside the **Intrastat Report**.

## Recalculate weight or supplementary unit of measure

If you got the error message *'Total Weight' in Intrastat Report Line must not be blank*, it's probably because you didn't set the **Net Weight** field on the used source, item, or fixed asset. In this case, search for the item or fixed asset card and add the required value. After that, you just need to reopen the **Intrastat Report** and follow these steps:

1. Choose the **Recalc. Weight/Suppl. UOM** action to recalculate the **Total Weight** and/or **Supplementary Quantity**.
2. Choose one of the options:

    1. **Weight** – to recalculate only the **Total Weight**, based on the current information about **Net Weight** on the item and fixed asset cards.
    2. **Supplemental UOM Qty** – to recalculate only the **Supplementary Quantity** on the **Intrastat Report** line if it exists, based on the current information about **Supplementary UOM** on the item and fixed asset cards.
    3. **Both** – to recalculate both **Total Weight** and **Supplementary Quantity**, based on the current information on the item and fixed asset cards.
3. Choose **OK** to start the batch job.

## Report Intrastat in a file

You can submit the Intrastat report as a file based on different local authorities' requirements. Before creating the file, you should run the **Checklist Report** to check if all lines contain all necessary and valid information. To create a file:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat List**, then choose the related link.
2. Choose **Intrastat Report** you want to report as a file.
3. If you haven't already done this, fill in the **Intrastat Report** manually or choose the **Suggest Lines** action.
4. Choose the **Create File** action.
5. The Intrastat file will be saved in the required format.

Once you create the file, [!INCLUDE[prod_short](includes/prod_short.md)] will automatically fill in the following details about reporting:

* The **Export Date** to specify the date when the report has been exported.
* The **Export Time** to specify the time when the report has been exported.

> [!NOTE]  
> Next time you create a file, the **Export Date** and **Export Time** fields will only keep information about the last file you created.

## Intrastat rules

### Grouping lines

In **Intrastat Report** lines, there's no grouping by any fields. All entries are copied from the original source, so you can quickly locate them based on the combination of **Source Type** and **Source Entry No**.

Grouping required by authorities will be provided in the exported file. You need to configure this in the **Data Exchange Definition**, which is fully configurable. Learn more at [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).

### Fixed assets reporting

Fixed assets will be shown in the Intrastat lines only if:

* The **FA Posting Type** in the **FA Ledger Entry** field is **Acquisition Cost** and if the **Document Type** is **Invoice** in the case of purchases, and
* The **FA Posting Type** in the **FA Ledger Entry** field is **Proceeds on Disposal** and if the **Document Type** is **Invoice** in the case of sales.

### Intrastat report statuses

When you work with the **Intrastat Report** you'll see a **Status** field on the document header. You can find the following statuses together with related rules:

* **Open**: This status is created automatically when you create a new Intrastat report and you can make all operations in this status.
* **Released**: [!INCLUDE[prod_short](includes/prod_short.md)] automatically changes the status to *Released* when you create a file. From that moment, you can't modify your **Intrastat Report**. If you need to change something and report again, you can use the **Reopen** action to reopen the Intrastat report. Once the document is reopened, you can use the **Release** action to release the document again.
* **Reported**: Specifies whether the entry has already been reported to the tax authorities. This isn't a regular status but an independent field, and even if you reopened the Intrastat report, it would still show that the file is already created for this report.

### Locations in Intrastat reporting 

[!INCLUDE[prod_short](includes/prod_short.md)] always uses the information in the **Country/Region Code** field on the **Location Card** page as the country for **send from** or for **receive to** goods. When this information doesn't exist or location wasn't used, the system uses the information from the **Company Information** page.   

> [!NOTE]  
> If the company operates from more than one country, Intrastat reporting desn't work for all countries where locations are configured. Reporting is based only for the main country, as it's not currently possible to use multi-country reporting.  

### Triangular trade in Intrastat

Triangular trade involves trade between three countries or regions where goods bypass the reporting company's country. In Business Central, this can be facilitated through the [Drop Shipment](sales-how-drop-shipment.md) functionality. To enable this option, activate the **Include Drop Shipment** field in the **Intrastat Report Setup**.  

When you enable this option, the system uses the following rules, but only if you have the **Drop Shipment** marked in the **Sales Order**: 

| Receiving from | Delivering to | Expected Intrastat Result |
|----------|------------|----------------------|
| Country as in the **Company Information** | Country as in the **Company Information** | No Intrastat lines |  
| Country as in the **Company Information** | EU country different from the country in the **Company Information** | Intrastat shipping line | 
| Country as in the **Company Information** | Non-EU country | No Intrastat lines |   
| EU country different from the country in the **Company Information** | Country as in the **Company Information** | Intrastat receiving line | 
| EU country different from the country in the **Company Information** | EU country different from the country in the **Company Information** | No Intrastat lines |
| EU country different from the country in the **Company Information** | Non-EU country | No Intrastat lines | 
| Non-EU country | Country as in the **Company Information** | No Intrastat lines |  
| Non-EU country | EU country different from the country in the **Company Information** | No Intrastat lines |
| Non-EU country | Non-EU country | No Intrastat lines |   

## Related information

[Set Up Intrastat Reporting](finance-how-setup-report-intrastat.md)    
[Financial Management](finance.md)    
[Drop Shipment](sales-how-drop-shipment.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
