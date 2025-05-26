---
title: Basic reports and documents output quick start
description: Business Central offers built-in templates for reports and documents, with many customization options to adapt them to your company's needs.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: quickstart
ms.search.form: 
ms.date: 05/17/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Basic reports and documents output quick start

To adapt [!INCLUDE[prod_short](includes/prod_short.md)] to your company needs, set and use reports and customized documents suited to your business' processes and visual identity.

## Add your company logo to documents

[!INCLUDE[prod_short](includes/prod_short.md)] has templates set to use your company's logo to save you time customizing documents such as invoices, orders, and statements.

1. Choose the ![Sprocket icon to open the Settings menu.](media/ui-experience/settings_icon_small.png) menu, then choose the **Company Information** action.
2. Choose the **Picture** action and then select **Choose**.
3. Select the picture file on your device.

After the image displays in the **Picture** field, you can close the **Company Information** page.

## Run reports

Reports organize information from different sources in [!INCLUDE[prod_short](includes/prod_short.md)] and present it in a readable way that can be easily printed or digitally shared. Reports can be found on the pages they're contextually associated with. For example, the **Items** page lists reports related to inventory levels, purchases, sales, and more.

1. Open the page associated with the requested report, such as the **Items** page.
2. Choose the **Inventory - Top 10 List** report on the **Reports** menu.
3. On the report request page, set filters to narrow down the date range or change the reference unit of measure used in the report.
4. Choose the **Print** action and follow the device's printing steps.
    1. Alternatively, select the **Preview** action to display the report on the screen.

Learn more on filtering data, scheduling reports, and more at [Run and Print Reports](ui-work-report.md).

## Save reports as PDF, Excel, or Word documents

To quickly share reports, you can save [!INCLUDE[prod_short](includes/prod_short.md)] reports directly to PDF, Microsoft Excel, or Microsoft Word documents.

1. Repeat steps 1 to 3 from the [run reports](#run-reports) section above.
2. Choose the **Send to** action.
3. Select the file type, then choose **OK**.
r
The generated report file is automatically saved to your browser's download folder.

### Change report and document layouts

[!INCLUDE[prod_short](includes/prod_short.md)] comes with many built-in layouts for your reports and other generated documents, such as sales invoices. You can use applications like Microsoft Word or Excel to edit the layout templates for documents and reports, as described in the following example:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layouts**, then choose the related link.
2. On the **Report Layouts** page, choose the **Search** action to select the *StandardSalesInvoice.docx* layout, then choose the **Export Layout** action to download the layout template file.

    A Word document is saved to your device, with the same filename displayed on the **Report Layouts** page.
3. Open the layout file in Microsoft Word and edit the document, for example, by moving the date field (*DocumentDate*) or your logo, or by changing font sizes, then save the file.
4. Back on the **Report Layouts** page, choose the **New Layout** action.
5. On the **Add New Layout for a Report** page, enter a name and description on the **Layout Name** and **Description** fields, respectively, to make the layout easy to find.
6. Select the **Word** option in the **Format Options** field, then choose **OK**.
7. On the **Choose Word Layout** page, select **Choose** to open the edited layout file on your device.
8. Test the new layout by choosing the **Run Report** action.

Learn more about how to customize reports and documents to your business needs at [Report and Document Layouts](ui-manage-report-layouts.md).

## Related information

[Use Reports in Daily Work](reports-use-reports.md)  
[Available Reports in [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md)  
[Document Report Selection](across-report-selections.md)  
[Business Central Quick Starts](quick-start-business-central.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
