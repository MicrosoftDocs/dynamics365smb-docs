---
title: "How to: Export Electronic Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic payments, exporting"
ms.assetid: 32033253-5567-43d5-824f-73e05e93ecc8
caps.latest.revision: 17
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# How to: Export Electronic Payments
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you can export payment journal entries into a file format according to four different payment standards. You must use the following windows to export according to the different payment standards.  
  
|Payment standard|Window to export from|  
|----------------------|---------------------------|  
|AEB N34|**Payment Orders**|  
|AEB N34.1|**Payment Orders**|  
|E\-PAY|**Payment Journal**|  
|SEPA|**Payment Journal** or **Payment Orders**|  
  
> [!IMPORTANT]  
>  Before you can export a payment, you must select a payment format in the **Payment Export Format** field in the **Bank Account Card** window.  
  
### To export electronic payments using the Payment Orders window  
  
1.  In the **Search** box, enter **Payment Orders**, and then choose the related link.  
  
2.  Select the documents that you want to pay.  
  
3.  On the **Home** tab, in the **Process** group, choose **Export to File**.  
  
     Payments of type SEPA will be exported to a file immediately.  
  
     Payments of type N34 or N34.1 will be exported when you run the **\($ B\_7000090 Payment order \- Export N34 $\)** or **\($ R\_7000060 PO \- Export N34.1 $\)** report, which automatically opens when you choose **Export** in step 3.  
  
4.  In the **\($ R\_7000060 PO \- Export N34.1 $\)** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_10721\_N\_2\_1100000 Bank Account No. $\)**|Select the bank account from which the payments will be exported.|  
    |**\($ R\_10721\_N\_2\_1100002 Settle Date $\)**|Specify the date that the export will be transmitted to the bank. This date will be the posting date for the payment journal entries that are exported.|  
    |**\($ R\_10721\_N\_2\_1100005 If Posting Date does not match Delivery Date $\)**|Specify if you want to match the settle date, or if you want to skip any payment journal lines where the entered posting date does not match the settle date.|  
    |**\($ R\_10721\_N\_2\_1100008 Expenses Code $\)**|Specify who is responsible for the payment expenses.|  
    |**\($ R\_10721\_N\_2\_1100010 Shared \(Only International Transf. $\)**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  
    |**\($ R\_10721\_N\_2\_1100013 Payment Order Concept.\) $\)**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**\($ R\_10721\_N\_2\_1100016 Relation $\)**|Specify if you want the bank to send you a detailed list of all transfer charges. If you do not select this field, the bank will send the total of all charges for all the transfers made.|  
    |**\($ R\_10721\_N\_2\_1100018 Number Of Copies $\)**|Specify the number of additional copies of the remittance advice that will be printed by this process. One document is always printed so that it can be mailed to the payee.|  
  
5.  Choose **Print** or **Preview** to see the created payment file.  
  
     The payment journal entries which have the **Bank Payment Type** field set to **Electronic Payment** will be exported. The data will be exported to a file that is formatted according the N34 or N34.1 standard format. In addition, remittance advice will be printed, which is suitable for mailing to each payee.  
  
    > [!NOTE]  
    >  You can only post the payment order after you have successfully exported the electronic payments.  
  
### To export electronic payments using the Payment Journal window  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  Select the documents that you want to pay.  
  
3.  On the **Navigate** tab, choose **Electronic Payments**, and then choose **Export**.  
  
     Payments of type SEPA will be exported to a file immediately.  
  
     Payments of type E\-PAY will be exported when you run the **Export Electronic Payments** report, which automatically opens when you choose **Export** in step 3.  
  
4.  In the **Export Electronic Payments** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_10721\_N\_2\_1100000 Bank Account No. $\)**|Select the bank account from which the payments will be exported.|  
    |**\($ R\_10721\_N\_2\_1100002 Settle Date $\)**|Specify the date that the export will be transmitted to the bank. This date will be the posting date for the payment journal entries that are exported.|  
    |**\($ R\_10721\_N\_2\_1100005 If Posting Date does not match Delivery Date $\)**|Specify if you want to match the settle date, or if you want to skip any payment journal lines where the entered posting date does not match the settle date.|  
    |**\($ R\_10721\_N\_2\_1100008 Expenses Code $\)**|Specify who is responsible for the payment expenses.|  
    |**\($ R\_10721\_N\_2\_1100010 Shared \(Only International Transf. $\)**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  
    |**\($ R\_10721\_N\_2\_1100013 Payment Order Concept.\) $\)**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**\($ R\_10721\_N\_2\_1100016 Relation $\)**|Specify if you want the bank to send you a detailed list of all transfer charges. If you do not select this field, the bank will send the total of all charges for all the transfers made.|  
    |**\($ R\_10721\_N\_2\_1100018 Number Of Copies $\)**|Specify the number of additional copies of the remittance advice that will be printed by this process. One document is always printed so that it can be mailed to the payee.|  
  
5.  Choose **Print** or **Preview** to see the created payment file.  
  
     The payment journal entries which have the **Bank Payment Type** field set to **Electronic Payment** will be exported. The data will be exported to a file that is formatted according to the selected payment standard. In addition, remittance advice will be printed, which is suitable for mailing to each payee.  
  
    > [!NOTE]  
    >  You can only post the payment order after you have successfully exported the electronic payments.  
  
    > [!NOTE]  
    >  In the generic version of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]-->, the **Payment Journal** window is used in a similar way to export electronic payments in the SEPA Credit Transfer format. For more information, see [Make Payments with Bank Data Conversion Service or SEPA Credit Transfer](../../Finance/make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).  
  
### To export electronic payments from the Cartera module  
  
1.  In the **Search** box, enter **PO \- Export N34.1**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_7000060\_N\_2\_1100000 Delivery Date $\)**|Specify the delivery date of the electronic payment.|  
    |**\($ R\_7000060\_N\_2\_1100002 Expenses Code $\)**|Specify who is responsible for the payment expenses.|  
    |**\($ R\_7000060\_N\_2\_1100007 Payment Order Concept $\)**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**\($ R\_7000060\_N\_2\_1100010 Relation $\)**|Specify if you want the bank to send you a detailed list of all transfer charges. If you do not select this field, the bank will send the total of all charges for all the transfers made.|  
    |**\($ R\_7000060\_N\_2\_1100012 Number Of Copies $\)**|Specify the number of additional copies of the remittance advice that will be printed by this process. One document is always printed so that it can be mailed to the payee.|  
    |**\($ R\_7000060\_N\_2\_1100004 Shared \(Only Internation Transf.\) $\)**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  
  
> [!NOTE]  
>  You can only post the payment order after you have successfully exported the electronic payments.  
  
## See Also  
 Payment Orders   
 Payment Journal   
 [Electronic Payments – AEB N34.1](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/electronic-payments-–-aeb-n34.1.md)   
 Export Electronic Payments   
 [How to: Set Up Bank Accounts for Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-set-up-bank-accounts-for-electronic-payments.md)   
 [Make Payments with Bank Data Conversion Service or SEPA Credit Transfer](../../Finance/make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)