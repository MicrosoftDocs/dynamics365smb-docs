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
# How to: Set Up Default Dimensions for One Account
You can set up a default dimension for a specific individual account. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will then copy this code to the journal, sales, or purchase line when the account number field is filled in on the line. However, you may delete or change the code if appropriate.  
  
 The following procedure is for setting up default dimension for a customer account.  
  
### To set up default dimensions for one account  
  
1.  In the **Search** box, enter **Customers** , and then choose the related link.  
  
2.  On the **Navigate** tab, in the **Customer** group, choose **Dimensions**.  
  
3.  Fill in a line for each new default dimension you want to set up. For Help about a specific field, click the field and press **F1**.  
  
> [!WARNING]  
>  If an account is used in the **Adjust Exchange Rates** batch job or the **Post Inventory Cost to G\/L** batch job, do not select **Code Mandatory** or **Same Code**. These batch jobs cannot use dimension codes.  
  
> [!IMPORTANT]  
>  Entering a code in the dimension field on the account card does not guarantee that the code will be used when you post. This is because it may be changed on the journal, sales, or purchase line. To make sure that that the code is not changed when you post, select the **Same Code** option.  
  
## See Also  
 [How to: Set Up Default or Required Dimensions for Account Types](../how-to-set-up-default-or-required-dimensions-for-account-types.md)   
 [How to: Set Up Global Dimensions](../how-to-set-up-global-dimensions.md)   
 [How to: Set Up Shortcut Dimensions](../how-to-set-up-shortcut-dimensions.md)   
 Default Dimension   
 Dimension   
 Adjust Exchange Rates   
 Post Inventory Cost to G-L