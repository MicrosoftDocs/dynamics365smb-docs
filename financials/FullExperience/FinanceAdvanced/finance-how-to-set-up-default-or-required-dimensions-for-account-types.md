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
# How to: Set Up Default or Required Dimensions for Account Types
You can set up a default dimension for an account type. ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> will then copy this code to the journal, sales or purchase line when the account type is filled in on the line. However, you may delete or change the code if appropriate.  
  
 You can also make a dimension required, so that it is not possible to post an entry with a specific type of account unless the account has a dimension value assigned to it.  
  
### To set up default or required dimensions for an account type  
  
1.  In the **Search** box, enter **Dimensions**, and then choose the related link.  
  
2.  In the **Dimensions** window, select the dimension.  
  
3.  On the **Navigate** tab, in the **Dimension** group, choose **Account Type Default Dim**.  
  
4.  Fill in a line for each new default dimension that you want to set up. ADD INCLUDE<!--[!INCLUDE[bp_fieldhelp]()]-->  
  
> [!TIP]  
>  If you want to make a dimension required but you do not want to assign a default value to the dimension, leave the **Dimension Value Code** field blank and then select **Code Mandatory** in the **Value Posting** field.  
  
> [!WARNING]  
>  If an account is used in the **Adjust Exchange Rates** batch job or the **Post Inventory Cost to G\/L** batch job, do not select **Code Mandatory** or **Same Code**. These batch jobs cannot use dimension codes.  
  
> [!NOTE]  
>  If an account must have a different dimension assigned to it than the default dimension already set up for the account type, you must set up a default dimension for this account. The default dimension for the individual account then replaces the default dimension for the account type.  
  
## See Also  
 [How to: Set Up Dimension Combinations](../how-to-set-up-dimension-combinations.md)   
 [How to: Set Up Default Dimensions for One Account](../how-to-set-up-default-dimensions-for-one-account.md)   
 [How to: Set Up Global Dimensions](../how-to-set-up-global-dimensions.md)   
 [How to: Set Up Shortcut Dimensions](../how-to-set-up-shortcut-dimensions.md)   
 Default Dimension   
 Dimension   
 Adjust Exchange Rates   
 Post Inventory Cost to G-L