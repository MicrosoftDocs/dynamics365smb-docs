---
title: Create a New Production BOM and BOM Version
description: Walkthrough to learn how to add another coffee maker to Contoso Coffee's product line in Business Central.
ms.date: 04/01/2022
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
---
# Walkthrough: Create a New Production BOM and BOM Version

In this article, we take you through the steps to use the Contoso Coffee demo data to work with bills of material (BOM) in production processes.  

## Scenario

Contoso Coffee has decided to add another coffee maker to their product line: **SP-SCM1008 Airpot Lite**. This coffee maker is identical to the existing item **SP-SCM1009 Airpot**, except that it does not include the warming plate, **SP-BOM1104**. In a separate step, the on/off light, **SP-BOM1106** is removed for a version of the Airpot Lite BOM.

Oscar, the process engineer at Contoso Coffee, must set up a new production BOM to define the initial component requirements for the Airpot Lite. Oscar must then set up a new BOM version, with a start date of July 01, to align with further plans on releasing another edition.

## Steps

1. Create a new production BOM for the Airpot Lite.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **production BOM**, and then choose the related link.  

    2. Choose the **New** action, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**No.** |SP-SCM1008|
        |**Description** |Airpot Lite|
        |**Unit of Measure Code**|PCS  |

2. Copy the BOM components from production BOM **SP-SCM1009**.

    1. Choose the **Copy BOM** action.

    2. In the **Production BOMs** page, choose the line for **SP-SCM1009, Airpot**, and then choose the **OK** button.

3. Change the components for the new production BOM as described in the scenario.

    1. On the **Lines** FastTab, select the line for the item **SP-BOM1104**, and then choose the **Delete Line** action.  

4. Certify the new BOM.  

    1. In the **Status** field, choose *Certified*.  

5. Create a production BOM version for the Airpot Lite.

    1. Choose the **Versions** action.

    2. On the **Prod. BOM Version List** page, choose the **New** action, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**Versions Code** |02|
        |**Description** |Airpot Lite, v2|
        |**Unit of Measure Code**|PCS  |  
        |**Starting Date**|July 01  |  

6. Copy the component lines from the production BOM into the new BOM version.

    1. Choose the **Copy BOM** action, and then choose the **Yes** button to copy the components from the original production BOM.

7. Remove the item **SP-BOM1106, On/off light** from  the version components.

8. Certify the new BOM version.

    1. In the **Status** field, choose *Certified*.  

    2. Close the BOM Version

The new coffee maker is now set up as a production BOM with one version.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
