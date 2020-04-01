---
    title: How to Set Up Bank Accounts for Electronic Payments
    description: In Business Central, you can set up bank accounts to make electronic payments.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Bank Accounts for Electronic Payments
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can set up bank accounts to make electronic payments.  

## To set up bank accounts for electronic payments  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Account Card**, and then choose the related link.  
2.  On the **Transfer** FastTab, make sure that the **CCC Bank No.**, **CCC Bank Branch No.**, **CCC Control Digits**, and **CCC Bank Account No.** fields are filled in correctly.  
3.  On the **Transfer** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**E-Pay Export File Path**|Enter the full path of the electronic payment file, start with the drive letter and end with a backslash (). The file name is not included here. You should use the directory where [!INCLUDE[d365fin](../../includes/d365fin_md.md)] is installed. For example: **C:NAV** would be a possible entry for this field. You can enter a maximum of 100 characters.|  
    |**Last E-Pay Export File Name**|Specify the name of the file with the .txt file name extension, without the path., Because the file name will be incremented every time that an electronic payment file is exported, this file name should have digits in it. This will create a permanent record of every file that you have exported to the bank. For example, **DD000000.txt** could be a possible first entry for this field. You can enter a maximum of 50 characters.|  

4.  On the **Posting** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Last Remittance Advice No.**|Specify a number series that differs from the check number series. This is needed so that the numbers do not conflict with each other. The remittance advice is printed on blank paper in a form that is easy to mail to the vendor.|  

## To set up vendor bank accounts for electronic payments  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendor Bank Account Card**, and then choose the related link.  
2.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Use For Electronic Payments**|Specify if this vendor bank account will be used for electronic payments. For electronic payments, only one bank account can be selected for each vendor.|  

3.  On the **Transfer** FastTab, make sure that the **CCC Bank No.**, **CCC Bank Branch No.**, **CCC Control Digits**, and **CCC Bank Account No.** fields are filled in correctly.  

## See Also  
 [Electronic Payments – AEB N34.1](electronic-payments-aeb-n341.md)
