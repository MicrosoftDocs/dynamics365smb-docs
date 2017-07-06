---
    title: How to: Set Up VAT Clauses | Microsoft Docs
    description: You set up a VAT clause to describe information about the type of VAT that is being applied. The information may be required by government regulation. After you set up a VAT clause, and associate it with a VAT posting setup, the VAT clause is displayed on all printed sales documents which have that VAT posting setup group, such as a sales invoice.
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
# How to: Set Up VAT Clauses
You set up a VAT clause to describe information about the type of VAT that is being applied. The information may be required by government regulation. After you set up a VAT clause, and associate it with a VAT posting setup, the VAT clause is displayed on all printed sales documents which have that VAT posting setup group, such as a sales invoice.  
  
### To set up VAT clause codes  
  
1.  In the **Search** box, enter **VAT Clauses**, and then choose the related link.  
  
2.  The **VAT Clauses** window opens. On a new line, in the **Code** field, enter a code for the clause. This code is used when you set up a VAT Posting group.  
  
3.  In the **Description** field, enter the text that you want to appear on VAT-related documents. In the **Description 2** field, enter additional text, if it is needed. The text will be displayed on a new line.  
  
4.  On the **Home** tab, in the **Process** group, choose **Setup**.  
  
5.  In the **VAT Posting Setup** window, you can set up a new posting group. On the **Home** tab, choose **New**.  
  
     Complete the setup by filling in the fields on the setup card. In the **VAT Clause Code** field, select a code that you have set up. For more information, see [How to: Create a VAT Combination Setup](../how-to-create-a-vat-combination-setup.md).  
  
6.  Choose the **OK** button.  
  
### To assign a VAT clause code to a posting group  
  
1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  Select the posting setup that you want to modify, and on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **General** FastTab, in the **VAT Clause Code** field, choose a code from the list.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [VAT Clauses](../vat-clauses.md)   
 VAT Clauses   
 VAT Posting Setup