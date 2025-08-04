---
title: Setting up norm jurisdictions in Russia
description: Russian enhancements include norm jurisdictions.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set Up Norm Jurisdictions

Norm jurisdictions are based on Russian tax laws that define a variety of tax rates. Norm jurisdictions are used to calculate taxable profits and losses in tax accounting. You can use the **Norm Jurisdictions** window to set up and define norm jurisdictions that can be used when you calculate tax differences.

## To set up norm jurisdictions

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Norm Jurisdictions**, and then choose the related link.

2. Enter an identifying **Code** and **Description** for the norm jurisdiction that you want to set up.

3. Choose the **Groups** action to open the **Norm Groups** window.

4. In the **Norm Groups** window, enter the following information.

   | Field              | Description                                                  |
   | :----------------- | :----------------------------------------------------------- |
   | **Code**           | Enter a code to identify the norm group.                     |
   | **Description**    | Enter a description for the norm group.                      |
   | **Has Details**    | Specifies if calculation details are defined for the norm group. |
   | **Search Detail**  | Select the method that you use for norm jurisdiction search. The options include **To Date** and **As of Date.** |
   | **Storing Method** | Select **Calculation** if the norm jurisdiction is calculated with a specific formula. Leave this field blank if the norm is a constant value. |

5. Choose the **Details** action to open the **Norm Details** window. In this window, you will define a constant tax rate for the norm.

6. In the **Norm Details** window, enter the following information.

   | Field              | Description                                                  |
   | :----------------- | :----------------------------------------------------------- |
   | **Effective Date** | Enter an effective date for the norm.                        |
   | **Norm**           | Enter a value for the norm. This value is used to calculate tax differences. |

7. Choose the **Close** button to close the **Norm Details** window and save your entries.

The norm jurisdiction that you set up is now available for use in calculating tax differences.

## Related information

[Tax Differences](Tax-Differences.md)  
[Setting up Tax Difference Calculation](Setting-up-Tax-Difference-Calculation.md)  
[Tax Accounting](Tax-Accounting.md)  
[Tax Registers](Tax-Registers.md)  
[Create Tax Registers](How-to-Create-Tax-Registers.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
