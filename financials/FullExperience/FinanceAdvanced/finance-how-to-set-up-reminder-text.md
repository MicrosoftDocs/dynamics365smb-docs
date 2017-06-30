---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up Reminder Text
For each reminder level, you can specify text that will be printed before or after the entries on the reminder.  
  
### To set up a reminder text  
  
1.  In the **Search** box, enter **Reminder Terms**, and then choose the related link.  
  
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
  
     For example, if you write **You owe %7 %9 due on %2.**, then the resulting reminder will contain the following text: **You owe 1.200,50 LCY due on 02-02-2014.**.  
  
## See Also  
 [How to: Create Reminders Automatically](../how-to-create-reminders-automatically.md)   
 [How to: Create Reminders Manually](../how-to-create-reminders-manually.md)   
 [How to: Set Up Reminder Levels](../how-to-set-up-reminder-levels.md)   
 [How to: Set Up Reminder Terms](../how-to-set-up-reminder-terms.md)