---
title: "How to: Create and Customize Miniforms"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "miniforms"
  - "automated data capture system, creating miniforms"
ms.assetid: 443638ed-1b6d-4ae9-a86e-7a393b261c80
caps.latest.revision: 8
ms.author: "edupont"
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
# How to: Create and Customize Miniforms
You use miniforms to describe the information that you want to present on a handheld device. For example, you can create miniforms to support the warehouse activity of picking items. After you create a miniform, you can add functions to it for the common actions that a user takes with handheld devices, such as moving up or down a line.  
  
 To implement or change the functionality of a miniform function, you must create a new codeunit or modify an existing one to perform the required action or response. You can learn more about ADCS functionality by examining codeunits such as 7705, which is the handling codeunit for logon functionality. Codeunit 7705 shows how a Card\-type miniform works. For more information, see [How to: Modify ADCS Functions](../Topic/How%20to:%20Modify%20ADCS%20Functions.md).  
  
### To create a miniform for ADCS  
  
1.  In the **Search** box, enter **ADCS**, and then choose the related link.  
  
2.  Choose **Miniforms**. The **Miniforms** window opens. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **General** FastTab, in the **Code** field, enter a code for the miniform. Optionally, enter values in all other fields.  
  
     Select the **Start Miniform** check box to indicate that the miniform is the first form that the user sees at logon.  
  
4.  In the **Lines** FastTab, define the fields that appear on the miniform. The order in which you enter lines is the order in which the lines appear on the handheld device.  
  
 After you have created a miniform, the next steps are to create functions and to associate functionality for various keyboard inputs.  
  
### To add support for a function key  
  
1.  Add code similar to the following example to the.xsl file for the plug\-in. This creates a function for the **F6** key. The key sequence information can be obtained from the device manufacturer.  
  
    ```  
    <xsl:template match="Function[.='F6']">  
      <Function Key1="27" Key2="91" Key3="49" Key4="55" Key5="126" Key6="0"><xsl:value-of select="."/></Function>  
    </xsl:template>  
  
    ```  
  
2.  In the [!INCLUDE[nav_dev_long](../BusinessFunctionality/DataExchange/includes/nav_dev_long_md.md)], open table 7702 and add a code representing the new key. In this example, create a key that is named **F6**.  
  
3.  Add C\/AL code to the relevant function of the miniform\-specific codeunit to handle the function key.  
  
### To customize miniform functions  
  
1.  In the **Search** box, enter **Miniforms**, and then choose the related link.  
  
2.  Select a miniform from the list. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Navigate** tab, choose **Functions**.  
  
4.  In the **\($ T\_7703\_2 Function Code $\)** drop\-down list, select a code to represent the function that you want to associate with the miniform. For example, you can select ESC, which associates functionality with the press of the ESC key.  
  
 In the [!INCLUDE[nav_dev_short](../LocalFunctionalityForMicrosoftDynamicsNav2016/includes/nav_dev_short_md.md)], edit the code for the **\($ T\_7700\_20 Handling Codeunit $\)** field to create or modify code to perform the required action or response.  
  
## See Also  
 [\($ N\_7700 Miniform $\)](../Topic/\($%20N_7700%20Miniform%20$\).md)   
 [\($ T\_7700\_13 Form Type $\)](../Topic/\($%20T_7700_13%20Form%20Type%20$\).md)