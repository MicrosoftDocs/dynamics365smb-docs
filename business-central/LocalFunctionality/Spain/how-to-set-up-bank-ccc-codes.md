---
    title: How to Set Up Bank CCC Codes
    description: Código Cuenta Cliente (CCC) is a unique account code used by banks to identify their customers. The CCC code is printed on bank documents such as checks and statements.

    services: project-madeira 
    documentationcenter: ''
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
# Set Up Bank CCC Codes
Código Cuenta Cliente (CCC) is a unique account code used by banks to identify their customers. The CCC code is printed on bank documents such as checks and statements.  

You can set up CCC codes in the following locations:  

- **Bank Account Card** page  
- **Company Information** page  
- **Customer Bank Account Card** page  
- **Vendor Bank Account Card** page  

The following procedure describes how to set up bank CCC codes for your company.  

## To enter CCC codes  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.  
2.  On the **Payments** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|--------------|---------------------------------------|  
    |**CCC Bank No.**|1-4|Identifies the bank where the account has been opened.|  
    |**CCC Bank Branch No.**|5-8|Identifies the branch code. If the bank does not use this reference, the branch code can be zeros.|  
    |**CCC Control Digits**|9-10|Identifies the control digits.|  
    |**CCC Bank Account No.**|11-20 (Spain)<br /><br /> 11-21 (Portugal)|Identifies the account number, which may be adjusted with preceding zeros.|  

The following procedure describes how to set up bank CCC codes for existing customer bank accounts, but the same steps apply to vendors, bank accounts, and company information.  

## To set up bank CCC codes for a customer bank account  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customer Bank Account Card**, and then choose the related link.  
2.  On the **Transfer** FastTab, enter information into the relevant CCC fields.  

    > [!NOTE]  
    >  You must set up the company information on the **Payments** FastTab.  

3.  Choose the **OK** button.  

## See Also  
[Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md) 
