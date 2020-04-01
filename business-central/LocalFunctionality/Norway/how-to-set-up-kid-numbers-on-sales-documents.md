---
    title: How to Set Up KID Numbers on Sales Documents
    description: Kunde ID (KID) is a customer identification number that provides a payment reference to the vendor and ensures that the vendor is posting the payment correctly.

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
# Set Up KID Numbers on Sales Documents
Kunde ID (KID) is a customer identification number that provides a payment reference to the vendor and ensures that the vendor is posting the payment correctly. You can set up KID numbers on sales documents to identify document and customer information on electronic banking transactions.  

## To set up KID numbers on sales documents  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
2.  On the **Documents** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**KID Setup**|Specifies a KID number format.|  
    |**Document No. length**|Enter the number of digits used for the document number.|  
    |**Customer No. length**|Enter the number of digits used for the customer number.|  
    |**Use KID on Fin. Charge Memo**|Select to print KID numbers on finance charge memos. **Note:**  If selected, then you must also select the **Document Type + Document No.** format in the **KID Setup** field.|  
    |**Use KID on Reminder**|Select to print KID numbers on reminders. **Note:**  If selected, then you must also select the **Document Type + Document No.** format in the **KID Setup** field.|

3.  Choose the **OK** button.  

## See Also  
 [Electronic Banking in Norway](electronic-banking-in-norway.md) 
