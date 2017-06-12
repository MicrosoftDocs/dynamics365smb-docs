---
title: "How to: Set Up Interest on Arrears"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "interest, on arrears"
ms.assetid: 4857a316-3179-4272-a043-f4e49f6f467f
caps.latest.revision: 22
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Set Up Interest on Arrears
For each finance charge term, you can specify how interest on arrears must be calculated. You can set up finance charge calculations with different interest rates for different periods.  
  
 When you apply a finance charge term with interest on arrears to a customer or vendor, interest on arrears will be calculated. Then, you can run the [Calculate Interest on Arrears](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-r_12107-calculate-interest-on-arrears-$-.md) report to view details about interest on arrears for customers or vendors.  
  
 After you run the report, if a customer owes interest on arrears, the information about the amount of interest on arrears to pay is added to the customer statement.  
  
### To set up interest on arrears  
  
1.  In the **Search** box, enter **Finance Charge Terms**, and then choose the related link.  
  
2.  In the **Finance Charge Terms** window, select the required finance charge term entry, and then, on the **Actions** tab, choose **Int. on Arrears**.  
  
3.  In the **Interest on Arrears** window, on the **Home** tab, choose **New**.  
  
4.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Specify the date from which you want to calculate interest on arrears. **Important:**  The start date for the first interest transaction cannot be later than the earliest posting date for the finance transactions.|  
    |**Interest Rate**|Specify the rate of interest to be calculated for the arrears.|  
    |**Description**|Specify the description for the interest on arrears.|  
  
5.  Choose the **OK** button.  
  
 The following procedure describes how to apply interest on arrears to a customer, but the same steps also apply for interest on arrears to a vendor.  
  
### To apply interest on arrears to a customer  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Select the customer to whom interest on arrears must be applied, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Payments** FastTab, in the **Int. on Arrears Code** field, select the appropriate finance charge term that includes interest on arrears.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Interest on Arrears Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/interest-on-arrears-overview.md)   
 [Finance Charge Terms](../Topic/\($%20N_6%20Finance%20Charge%20Terms%20$\).md)   
 [Interest on Arrears Window](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-n_12101-interest-on-arrears-window-$-.md)   
 [Int. on Arrears Code](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-t_18_12100-int.-on-arrears-code-$-.md)   
 [Calculate Interest on Arrears](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-r_12107-calculate-interest-on-arrears-$-.md)