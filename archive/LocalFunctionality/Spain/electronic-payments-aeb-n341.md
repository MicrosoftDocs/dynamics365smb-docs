---
    title: Electronic Payments – AEB N34.1
    description: With the electronic payments functionality, you can pay vendors using electronic payments rather than printing paper checks. Electronic payments are exported into a standard AEB N34.1 file format used by most banks in Spain.

    documentationcenter: ''
    author: SorenGP

    ms.prod: "dynamics-nav-2017"
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Electronic Payments – AEB N34.1
With the electronic payments functionality, you can pay vendors using electronic payments rather than printing paper checks. Electronic payments are exported into a standard AEB N34.1 file format used by most banks in Spain. This file is then transmitted to your bank.  

You can create electronic payments from the payment journals or from the Cartera functionality (report list). This is intended to cover the following cases:  

- Invoices and open, non-grouped Cartera documents. If you select to pay using electronic payments, then the payment file is generated from the **Export Electronic Payments** report.  

- Invoices and Cartera documents that are grouped in a payment order. If you select to pay using electronic payments, the payment file is generated from the **PO - Export N34.1** report, available in the Cartera report list.  

> [!NOTE]  
>  Partners may need to modify this report to meet their customer’s bank individual requirements.  

Before you can transfer payments electronically to a vendor, you will need to set up a bank account for the vendor. You will also need to set up the electronic payment links with your bank and set up the bank account card in [!INCLUDE[navnow](../../includes/navnow_md.md)] for your own bank to handle the electronic payments. The bank should provide the transmission program.  

## See Also  
 [How to: Set Up Bank Accounts for Electronic Payments](how-to-set-up-bank-accounts-for-electronic-payments.md)   
 [How to: Pay Vendors by Using Electronic Payments](how-to-pay-vendors-by-using-electronic-payments.md) 
