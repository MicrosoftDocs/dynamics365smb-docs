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
# How to: Set Up KID Numbers on Sales Documents
Kunde ID \(KID\) is a customer identification number that provides a payment reference to the vendor and ensures that the vendor is posting the payment correctly. You can set up KID numbers on sales documents to identify document and customer information on electronic banking transactions.  
  
### To set up KID numbers on sales documents  
  
1.  In the **Search** box, enter **Sales & Receivables Setup**, and then choose the related link.  
  
2.  On the **Documents** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**KID Setup**|Specifies a KID number format.|  
    |**Document No. length**|Enter the number of digits used for the document number.|  
    |**Customer No. length**|Enter the number of digits used for the customer number.|  
    |**Use KID on Fin. Charge Memo**|Select to print KID numbers on finance charge memos. **Note:**  If selected, then you must also select the **Document Type \+ Document No.** format in the **KID Setup** field.|  
    |**Use KID on Reminder**|Select to print KID numbers on reminders. **Note:**  If selected, then you must also select the **Document Type \+ Document No.** format in the **KID Setup** field.|  
    |**Print Receipt on Giro**|Select to print the receipt section on sales invoices, credit memos, reminders, or finance charge memos.There are several layout options available when printing the receipt section on sales documents that contain a Giro. For more information, see [Norwegian Sales Documents](norwegian-sales-documents.md)|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Electronic Banking in Norway](electronic-banking-in-norway.md)   
 [\($ T\_311 Sales & Receivables Setup $\)](\($%20T_311%20Sales%20&%20Receivables%20Setup%20$\).md)   
 [Norwegian Sales Documents](norwegian-sales-documents.md)