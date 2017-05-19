---
title: "How to: Create Account Schedule Columns That Calculate Percentages"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "account schedules, calculating percentages"
  - "account schedules (columns), creating for calculation percentages"
ms.assetid: dd672177-efd9-4d63-a96a-2327af91448d
caps.latest.revision: 6
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Create Account Schedule Columns That Calculate Percentages
Sometimes you may want to include a column in an account schedule to calculate percentages of a total. For example, if you have a number of rows that break down sales by dimension, you may want a column to indicate the percentage of total sales that each row represents.  
  
### To create a column that calculates percentages  
  
1.  In the **Search** box, enter **Account Schedules**, and then choose the related link.  
  
2.  In the **Account Schedule Names** window, select an account schedule.  
  
3.  On the **Home** tab, in the **Process** group, choose **Edit Account Schedule** to set up an account schedule row to calculate the total on which the percentages will be based.  
  
4.  Insert a line immediately above the first row for which you want to display a percentage.  
  
     Fill in the fields on the line. In the **Totaling Type** field, enter **Set Base for Percent**. In the **Totaling** field, enter a formula for the total that the percentage will be based on. For example, if row 11 contains the total sales, enter **11**.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Edit Column Layout Setup** to set up a column.  
  
     Fill in the fields on the line. In the **Column Type** field, select **Formula**. In the **Formula** field, enter a formula for the amount that you want to calculate a percentage for, followed by %. For example, if column number N contains the net change, enter **N%**.  
  
 Repeat this procedure for each group of rows that you want to break down by percentage.  
  
## See Also  
 [How to: Change Column Layouts in Account Schedules](../BusinessIntelligence/how-to-change-column-layouts-in-account-schedules.md)   
 [How to: Set Up Account Schedule Columns Manually](../BusinessIntelligence/how-to-set-up-account-schedule-columns-manually.md)   
 [How to: Set Up Account Schedule Rows Manually](../BusinessIntelligence/how-to-set-up-account-schedule-rows-manually.md)   
 [How to: Set Up Account Schedules with Overviews](../BusinessIntelligence/how-to-set-up-account-schedules-with-overviews.md)   
 [How to: Create New Account Schedules](../BusinessIntelligence/how-to-create-new-account-schedules.md)