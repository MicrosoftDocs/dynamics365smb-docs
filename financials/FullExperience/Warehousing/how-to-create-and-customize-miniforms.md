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
# How to: Create and Customize Miniforms
You use miniforms to describe the information that you want to present on a handheld device. For example, you can create miniforms to support the warehouse activity of picking items. After you create a miniform, you can add functions to it for the common actions that a user takes with handheld devices, such as moving up or down a line.  
  
 To implement or change the functionality of a miniform function, you must create a new codeunit or modify an existing one to perform the required action or response. You can learn more about ADCS functionality by examining codeunits such as 7705, which is the handling codeunit for logon functionality. Codeunit 7705 shows how a Card-type miniform works. For more information, see [How to: Modify ADCS Functions](../How%20to:%20Modify%20ADCS%20Functions.md).  
  
### To create a miniform for ADCS  
  
1.  In the **Search** box, enter **ADCS**, and then choose the related link.  
  
2.  Choose **Miniforms**. The **Miniforms** window opens. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **General** FastTab, in the **Code** field, enter a code for the miniform. Optionally, enter values in all other fields.  
  
     Select the **Start Miniform** check box to indicate that the miniform is the first form that the user sees at logon.  
  
4.  In the **Lines** FastTab, define the fields that appear on the miniform. The order in which you enter lines is the order in which the lines appear on the handheld device.  
  
 After you have created a miniform, the next steps are to create functions and to associate functionality for various keyboard inputs.  
  
### To add support for a function key  
  
1.  Add code similar to the following example to the.xsl file for the plug-in. This creates a function for the **F6** key. The key sequence information can be obtained from the device manufacturer.  
  
    ```  
    <xsl:template match="Function[.='F6']">  
      <Function Key1="27" Key2="91" Key3="49" Key4="55" Key5="126" Key6="0"><xsl:value-of select="."/></Function>  
    </xsl:template>  
  
    ```  
  
2.  In the ADD INCLUDE<!--[!INCLUDE[nav_dev_long](../../includes/nav_dev_long_md.md)]-->, open table 7702 and add a code representing the new key. In this example, create a key that is named **F6**.  
  
3.  Add C\/AL code to the relevant function of the miniform-specific codeunit to handle the function key.  
  
### To customize miniform functions  
  
1.  In the **Search** box, enter **Miniforms**, and then choose the related link.  
  
2.  Select a miniform from the list. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Navigate** tab, choose **Functions**.  
  
4.  In the **Function Code** drop-down list, select a code to represent the function that you want to associate with the miniform. For example, you can select ESC, which associates functionality with the press of the ESC key.  
  
 In the ADD INCLUDE<!--[!INCLUDE[nav_dev_short](../../includes/nav_dev_short_md.md)]-->, edit the code for the **Handling Codeunit** field to create or modify code to perform the required action or response.  
  
## See Also  
 Miniform   
 Form Type