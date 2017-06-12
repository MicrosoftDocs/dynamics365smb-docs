---
title: "How to: Set Up Reminder Text"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reminders, setting up"
  - "overdue, setting up reminder text"
ms.assetid: dd990c04-4240-449b-ad1a-258ffd9154bd
caps.latest.revision: 10
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
  - "en-nz"
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
# How to: Set Up Reminder Text
For each reminder level, you can specify text that will be printed before or after the entries on the reminder.  
  
### To set up a reminder text  
  
1.  In the **Search** box, enter **\($ N\_431 Reminder Terms $\)**, and then choose the related link.  
  
2.  In the **Reminder Terms** window, on the **Actions** tab, in the **General** group, choose **Levels**.  
  
3.  In the **Reminder Levels** window, on the **Navigate** tab, in the **Level** group, choose **Beginning Text** or **Ending Text**, depending on what kind of text you want to specify.  
  
4.  In the **Text** field, enter one or more lines of text. Each line can contain up to 100 characters, but depending on the width of the individual characters there may not be enough room on the paper to print all of them.  
  
### Use placeholders to insert values in the text  
  
-   To automatically insert related values in the resulting reminder text, enter the following placeholders in the **Text** field.  
  
    |Placeholder|Value|  
    |-----------------|-----------|  
    |%1|Content of the **Document Date** field on the reminder header|  
    |%2|Content of the **Due Date** field on the reminder header|  
    |%3|Content of the **Interest Rate** field on the related finance charge terms|  
    |%4|Content of the **Remaining Amount** field on the reminder header|  
    |%5|Content of the **Interest Amount** field on the reminder header|  
    |%6|Content of the **Additional Fee** field on the reminder header|  
    |%7|The total amount of the reminder|  
    |%8|Content of the **Reminder Level** field on the reminder header|  
    |%9|Content of the **Currency Code** field on the reminder header|  
    |%10|Content of the **Posting Date** field on the reminder header|  
    |%11|The company name|  
    |%12|Content of the **Add. Fee per Line** field on the reminder header|  
  
     For example, if you write **You owe %7 %9 due on %2.**, then the resulting reminder will contain the following text: **You owe 1.200,50 LCY due on 02\-02\-2014.**.  
  
## See Also  
 [How to: Create Reminders Automatically](../Finance/how-to-create-reminders-automatically.md)   
 [How to: Create Reminders Manually](../Finance/how-to-create-reminders-manually.md)   
 [How to: Set Up Reminder Levels](../Finance/how-to-set-up-reminder-levels.md)   
 [How to: Set Up Reminder Terms](../Finance/how-to-set-up-reminder-terms.md)