---
    title: Summarizing Payment Lines and General Journal Lines
    description: In [!INCLUDE[d365fin](../../includes/d365fin_md.md)] handles several types of transactions in the same way.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Summarizing Payment Lines and General Journal Lines
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)] handles the following types of transactions in the same way:  

- Domestic payments  
- International payments  
- SEPA payments  
- Non-euro SEPA payments  

## How Payment Journal Lines are Transferred to the General Journal  
When you export the payment journal lines to a file, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] transfers the payment journal lines to the specified general journal. By default, a general journal line is created for each payment journal line.  

The following two fields in the **Electronic Banking Setup** window affect how the payment lines are summarized:  

- **Summarize Gen. Jnl. Lines**  
- **Cut off Payment Message Texts**  

If you have selected the **Summarize Gen. Jnl. Lines** check box in the **Electronic Banking Setup** window, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] summarizes all payment journal lines for a specific vendor into one general journal line. The general description "Payment %1," where %1 is the vendor number, is used for the summarized journal line description. A separate payment line and a separate general journal line are created to handle:  

- Payment journal lines that contain partial payments, with both the **Partial Payment** and the **Separate Line** fields selected.  

- Payment journal lines that contain a standard format message (that is, passes the MOD97 test), which sets **Standard Format Message** to True in the electronic banking journal.  

## Example 1  
In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** check box is selected. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] creates:  

- One combined payment line in a XML file that has a concatenated payment message. White space is the delimiter.  
- One payment line in the general journal with a generic description that ../../includes the vendor name.  

## Example 2  
In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** check box is selected. The **Cut off Payment Message Texts** check box is cleared, and combined SEPA and non-euro SEPA payment lines exceed 140 characters in payment message. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] creates:  

- Two combined payment lines in a XML file. The first payment line contains the first concatenated payment messages. The second payment line contains the payment message from the third line.  

- One payment line in the general journal with a generic description that ../../includes the vendor name.  

## Example 3  
In this example, you export payment lines, and the **Summarize Gen. Jnl. Lines** check box is selected. The **Cut off Payment Message Texts** check box is also selected and combined SEPA and non-SEPA payment lines exceed 140 characters in payment message. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] creates:  

- One combined payment line in a XML file that has two concatenated payment messages. An ellipsis (…) is used to indicate that the message is truncated.  

- One payment line in the general journal with a generic description that includes the vendor name.  

Based on the XML structure, the payments are summarized per account number and beneficiary bank account no and bank account no. The bank account filter can be empty.  

The EndToEndId in the SEPA message is taken from the payment message and can be truncated to the maximum length of 45 characters.  

## See Also  
 [Set Up Electronic Banking](how-to-set-up-electronic-banking.md)   
 [Setting Up Finance](../../finance-setup-finance.md)  
 [Record Purchases](../../purchasing-how-record-purchases.md) 
