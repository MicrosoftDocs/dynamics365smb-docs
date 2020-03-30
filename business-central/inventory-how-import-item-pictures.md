---
title: Importing Many Item Pictures from a ZIP File| Microsoft Docs
description: You can import multiple item pictures in one go. Simply name your picture files with names corresponding to your item numbers, compress them to a zip file, and then use the Import Item Pictures page to manage which item pictures to import.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: product, image
ms.date: 04/01/2020
ms.author: sgroespe

---
# Import Multiple Item Pictures
You can import multiple item pictures in one go. Simply name your picture files with names corresponding to your item numbers, compress them to a ZIP file, and then use the **Import Item Pictures** page to manage which item pictures to import.

All common file formats are supported.

## To name picture files by the item names and prepare the ZIP file
1. At the location where your item pictures are stored, name each files according to the number of the related item. For example:

    |Item No.|File Name|
    |-|-|
    |1000|1000.bmp|
    |1001|1001.bmp|
    |1002|1002.bmp|

2. Collect all the files in a ZIP file. For example, in Windows Explorer, select the files, and then choose **Send to**, **Compressed (zipped) folder**.     

## To import item pictures
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.
2. Choose the **Import Item Pictures** action.
3. In the **Select a ZIP file** field, select the relevant ZIP folder, and then choose the **Open** button.

    A line for each item and picture is created on the **Import Item Pictures** page.

    > [!NOTE]
    > For item cards that already have a picture, the **Picture Already Exists** check box is selected. If you do not want any existing pictures to be replaced, deselect the **Replace Pictures** check box. If you do not want individual existing pictures to be replaced, delete the lines in question.

3. Choose the **Import Pictures** action.

The **Import Status** field is updated to show if the picture import was skipped or completed.       

## See Also
[Register New Items](inventory-how-register-new-items.md)  
[Create Number Series](ui-create-number-series.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
