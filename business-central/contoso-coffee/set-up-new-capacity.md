---
title: Set Up New Capacity 
description: Walkthrough to learn how to set up a new work center with a capacity calendar for a single shift in Business Central.
ms.date: 03/10/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Walkthrough: Set Up New Capacity

Intro

## Scenario

You are the production planner at CONTOSO. In response to changes on the shop floor, you must set up a new work center called "Testing Department". The new work center has one machine center, which is named "Testing". The new centers must have a capacity calendar for a single shift from 08:00:00 AM to 4:00:00 PM, Monday to Friday.

## Steps

1. Set up the work center.

    1. In the **Tell Me** window, type "work centers", and then select the related link.

    2. Create a new work center.

    3. In the **No.**, field, type "700".

    4. In **Name** field, type "Testing Department".

    5. In the **Work Center Group Code** field, select 1, Production department.

    6. In the **Direct Unit Cost** field, type "3.25".

    7. In the **Unit Cost Calculation** field, select Time.

    8. In the **Flushing Method** field, select Manual.

    9. In the **Gen. Prod. Posting Group** field, select NO VAT. Note that this selection depends on your accounting setup/localization.

    10. In the **Unit of Measure Code** field, select MINUTES.

    11. In the **Capacity** field, type "1".

    12. In the **Efficiency** field, type "90".

    13. In the **Shop Calendar Code** field, select 1, for one shift from Monday to Friday.

    14. Close the work center card.

2\. Set up the machine center.

1. In the **Tell Me** window, type "machine centers", and then select the related link.

2. Create a new machine center.

3. In the **No.** field, type "760".

4. In the **Name** field, type "Testing".

5. In the **Work Center No.** field, select 700, Testing Department.

6. In the **Direct Unit Cost** field, type "3.25".

7. In the **Flushing Method** field, select Manual.

8. In the **Gen. Prod. Posting Group** field, select NO VAT. Note that this selection depends on your accounting setup.

9. In the **Capacity** field, type "1".

10. In the **Efficiency** field, type "90".

11. Expand the **Routing Setup** FastTab.

12. In the **Setup** Time field, type "10".

3\. Calculate the machine center capacity calendar.

1. Choose **Calendar** action.

2. On the **Matrix Options** FastTab of the **Machine Center Calendar** page, in the **View by** field, select Month.

3. Choose **Show Matrix** action.

4. On the **Machine Center Calendar Matrix** page, choose **Calculate** action.

5. On the **Options** FastTab of the **Calc. Machine Center Calendar** page, set the **Starting Date** field to January 01.

6. Set the **Ending Date** field to December 31.

7. On the **Machine Center** FastTab, in the **No.** filter field, select 760, Testing.

8. Choose **OK** to start the batch job. After the batch job finishes, it returns you to the **Machine Center Calendar Matrix** page.

9. On the **Actions** tab, choose **Refresh** action.

10. On the line for machine center 760, Testing, drill down into the value in the January column.

11. On the **Calendar Entries** page, notice that the daily capacity entries in the **Capacity (Total)** field are for 480 minutes. This reflects one eight-hour shift for each work day. Also notice that the values in the **Capacity (Effective)** field are 432 minutes. This reflects the 90 percent efficiency rate that you assigned to the machine center.


