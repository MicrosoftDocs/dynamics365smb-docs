---
title: Fixed asset inventory in Russia
description: Russian enhancements include fixed asset inventory.
author: DianaMalina


ms.topic: article
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Fixed Asset Inventory

The fixed assets inventory feature enables you to:

- Process inventory auditing of fixed assets in accordance with legal requirements.
- Generate electronic inventory lists of fixed assets that are to be inventoried with calculated quantities and amounts.
- Divide the inventory lists by the physical locations of fixed assets (by Fixed Asset Location code).
- Filter the inventory lists by other analytics (such as responsible employee).
- Print the forms with inventory lists that show all inventoried fixed assets, as well as lists that show the fixed assets with differences only in quantities or amounts.
- Print unified fixed asset forms.



## Inventory Lists of Fixed Assets

You must create inventory lists of fixed assets with calculated quantities and amounts for inventory auditing. The lists are divided by analytics such as physical locations and employees responsible for certain fixed assets.

You can create special templates in the **Fixed Asset Journal** window.

The following procedure shows how to generate a list of fixed assets that are to be inventoried.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Journals**, and then choose the related link.

2. Choose the **Calculate FA** action. The request form of a report that makes fixed asset inventory lists is displayed.

3. On the **Fixed Asset** FastTab, filter the fixed assets.

   > [!NOTE]
   > They can be filtered by any parameter from the Fixed Asset card, such fixed asset location or responsible employee.

The parameters listed in the following table are on the **Options** FastTab.

| Parameter                                | Description                                                  |
| :--------------------------------------- | :----------------------------------------------------------- |
| **Fixed Asset Journal Template**         | Select the fixed asset journal template to work with the fixed assets list during the inventory auditing process. It is filled by default with the fixed asset journal template. |
| **Depreciation Book Code**               | Select the depreciation book with the records, which will be calculated by quantities and amounts. |
| **Starting Document No.**                | Specify the document number used to make lines in the fixed asset journal. |
| **Document Date**                        | Specify the document date.                                   |
| **Posting Date**                         | Specify the posting date. The quantities and amounts are calculated on this date. The **Posting Date** field is also filled with this value. |
| **Show Fixed Asset with Book Value = 0** | Select this field to create fixed asset journal lines for fixed assets which have a book value of zero. |

The report creates one batch in the fixed asset journal template for every fixed asset location that is filtered in the request form. For every fixed asset that is filtered, one journal line is created in the batch according to its location. A journal batch is created for fixed assets in each fixed asset location.

The following procedure shows how to begin inventory auditing by fixed asset locations.

1. Select the batch according to the fixed asset location, and choose **ОК**.

   > [!NOTE]
   > You can view the fixed assets lines that are filtered in the report and the lines that are in this fixed asset location.

2. Place the columns of the fixed asset journal so that you can view calculated and actual quantities and amounts. They are reflected in the following fields:

   - **Actual Quantity**
   - **Calc. Quantity**
   - **Actual Amount**
   - **Calc. Amount**



> [!NOTE]
> The amount value is the book value of the fixed asset.





## Related information

[Fixed Asset Locations and Employees](Fixed-Asset-Locations-and-Employees.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
