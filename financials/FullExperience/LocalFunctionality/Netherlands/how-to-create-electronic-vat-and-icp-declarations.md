---
title: "How to: Create Electronic VAT and ICP Declarations"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic declarations, creating"
  - "electronic declarations, submitting"
  - "electronic declarations, VAT"
ms.assetid: e7a12268-0421-4fe4-a354-8ab0d8128420
caps.latest.revision: 26
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Create Electronic VAT and ICP Declarations
To create electronic VAT and ICP declarations, you must first set up the declaration using the **Elec. Tax Declaration Setup** window. Then you can submit them to the tax authorities.  
  
> [!NOTE]  
>  If you have selected the **Part of Fiscal Entity** field in the **Elec. Tax Declaration Setup** window, then you can create an electronic declaration for only one company. If you want to combine the tax information for all subsidiaries of a holding company, you must create a VAT statement on paper for each subsidiary company and manually calculate the total amounts for the holding company. These total amounts of the holding company must be entered on the website of the tax authorities. You cannot combine tax information for ICP declarations. ICP declarations must always be submitted individually.  
  
 If there are no intra\-community deliveries in the declaration period, then an electronic ICP declaration is created without XML elements for the deliveries. If you submit such a declaration, an error message will be displayed.  
  
### To create an electronic VAT or ICP declaration  
  
1.  In the **Search** box, enter **Elec. Tax Declarations**, and then choose the related link.  
  
2.  In the **Elec. Tax Declaration List** window, on the **Home** tab, choose **New**.  
  
3.  In the **Elec. Tax Declaration Card** window, on the **General** FastTab, fill in the required fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Declaration Type**|Select the type of electronic declaration you want to create. The options include **VAT Declaration** and **ICP Declaration**.|  
    |**No.**|The number for the electronic declaration.|  
    |**Declaration Period**|The period for which you want to create the electronic declaration.<br /><br /> For ICP declarations, the period is only for a quarter.|  
    |**Declaration Year**|The year for which you want to create the electronic declaration.|  
    |**Message ID**|Displays the ID of the response message received from the tax authority.<br /><br /> [!INCLUDE[bp_fieldnoneditable](../../Finance/includes/bp_fieldnoneditable_md.md)]<br /><br /> You must refer to this ID when you contact the tax authorities for any questions regarding your electronic declaration.|  
    |**Status**|The status of the electronic declaration. For more information, see Status Field.<br /><br /> [!INCLUDE[bp_fieldnoneditable](../../Finance/includes/bp_fieldnoneditable_md.md)]|  
    |**Our Reference**|The unique identification for the electronic declaration that is to be included in the electronic declaration file. This field must be exactly 11 characters, must start with OB\-, and can only contain numbers, letters, and dashes.<br /><br /> You cannot change this field after you have created the electronic declaration.|  
    |**Date Created**|The date on which the electronic declaration was created.<br /><br /> [!INCLUDE[bp_fieldnoneditable](../../Finance/includes/bp_fieldnoneditable_md.md)]|  
    |**Date Submitted**|The date on which the electronic declaration is submitted to the tax authorities.<br /><br /> [!INCLUDE[bp_fieldnoneditable](../../Finance/includes/bp_fieldnoneditable_md.md)]|  
    |**Date Received**|The date on which a response message from the tax authorities' for an electronic declaration is processed.<br /><br /> [!INCLUDE[bp_fieldnoneditable](../../Finance/includes/bp_fieldnoneditable_md.md)]|  
  
4.  On the **Home** tab, in the **Process** group, choose **Create Electronic Tax Declaration**.  
  
5.  In the **Create Elec. VAT Declaration** or the **Create Elec. ICP Declaration** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Template Name**|The name of the template that will be used to create the electronic declaration.|  
    |**Statement Name**|The name of the statement that will be used to create the electronic declaration.|  
  
6.  Choose the **OK** button.  
  
     The XML elements and the accompanying data of the electronic declaration are displayed on the **Lines** FastTab in the **Elec. Tax Declaration Card** window.  
  
## See Also  
 [Electronic Tax Declarations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/electronic-tax-declarations.md)   
 [Electronic VAT and ICP Declarations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/electronic-vat-and-icp-declarations.md)   
 [How to: Set Up VAT Categories](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-set-up-vat-categories.md)   
 Status Field   
 Part of Fiscal Entity Field