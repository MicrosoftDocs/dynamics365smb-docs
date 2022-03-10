---
title: Create a New Production BOM and BOM Version
description: Walkthrough to learn how to add another coffee maker to Contoso Coffe's product line in Business Central.
ms.date: 03/10/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Walkthrough: Create a New Production BOM and BOM Version

Intro

## Scenario

CONTOSO has decided to add another Coffee Maker to its product line: item SP-SCM1008, Airpot Lite. This coffee maker is identical to item SP-SCM1009, Airpot, except that it also does not have Warming plate (item SP-BOM1104). Later the On/off light (item SP-BOM1106) will be also removed, this will be handled as a second version of the Airpot Lite BOM.

Oscar, the process engineer at CONTOSO, must set up a new production BOM to define the initial component requirements for the Airpot Lite. He must then set up a new BOM version, with a starting date of July 01, to align with further plans on releasing another edition.

## Steps

1. Create a new production BOM for the Airpot Lite.

    1. In the **Tell Me** window, type "production BOM", and then select the related link.

    2. Create a new Bill of Material.

    3. In the **No.** field, type "SP-SCM1008" or let system assign number automatically.

    4. In the **Description** field, type "Airpot Lite".

    5. In the **Unit of Measure Code** field, select PCS.

2. Copy the BOM components from production BOM SP-SCM1009.

    1. Choose **Copy BOM** action.

    2. On the **Production BOMs** page, select the line for BOM SP-SCM1009, Airpot.

3. Change the components for the new production BOM as described in the scenario.

    1. On the **Lines** FastTab of the **Production BOM** page, select line for item SP-BOM1104, and then click **Delete** Line.

4. Certify the new BOM.

    1. In the **Status** field, select Certified.

5. Create a new production BOM version for the Airpot Lite.

    1. Choose **Versions** action.

    2. On the **Prod. BOM Version List** page, choose **New** action.

    3. In the **Versions Code** field, type "02".

    4. In the **Description** field, type "Airpot lite, v2".

    5. In the **Unit of Measure Code** field, select PCS.

    6. In the **Starting Date** field, select July 01.

6. Copy the component lines from the production BOM into the new BOM version.

    1. Choose **Copy BOM** action.

    2. On the request message, click **Yes** to copy the components from the production BOM.

7. Remove item SP-BOM1106, On/off light, to the version components.

8. Certify the new BOM version.

    1. In the **Status** field, select Certified.

    2. Close the BOM Version


