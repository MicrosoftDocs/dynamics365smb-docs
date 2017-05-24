---
title: "How to: Set Up Electronic Banking"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic banking, in Belgium"
  - "electronic banking, setting up"
  - "bank accounts, setting up preferred accounts"
ms.assetid: ecefd58c-77e8-47cd-b508-c701cf21733d
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Set Up Electronic Banking
With electronic banking, you can make electronic payments to domestic, international, SEPA, and non\-Euro SEPA vendors and customers.  
  
 Your company subscribes to an eBanking contract with the bank to maintain a certain bank account or several bank accounts. The company also subscribes to Isabel to send payment files to and receive bank statement files from the bank electronically. Therefore, the company receives smartcards linked to the eBanking contract. The smartcards are secured by PIN codes.  
  
 You will receive one of these smartcards to connect to IBS so that you are connected to the eBanking contract of the company.  
  
 When uploading to or downloading files from the IBS platform, you will insert the smartcard in the card reader and use a PIN code to make connection to IBS. When the IBS session is established, the eBanking contract and eBanking user is known by the system. Also the eBanking contract and user linked bank account numbers are known.  
  
 Before you can use electronic banking, you must set up the following information:  
  
-   Electronic banking setup.  
  
-   IBLC\/BLWI codes \- For more information, see [How to: Set Up IBLC\-BLWI Transaction Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-iblc-blwi-transaction-codes.md).  
  
-   Preferred bank accounts \(optional\).  
  
### To set up electronic banking  
  
1.  In the **Search** box, enter **Electronic Banking Setup**, and then choose the related link.  
  
2.  In the **Electronic Banking Setup** window, on the **General** FastTab, fill in the fields as described in the following table. [!INCLUDE[bp_fieldhelp]()]  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11306\_2 Summarize Gen. Jnl. Lines $\)**|Select to indicate if you want to group the payment journal lines for each vendor.|  
    |**\($ T\_11306\_3 Cut off Payment Message Texts $\)**|Select to indicate if you want to truncate long payment messages. Messages will be truncated if greater than 106 characters for domestic payments and less than 140 characters for international payments.|  
    |**\($ T\_11306\_21 IBS Version $\)**|Specify the version of Isabel that is currently used for electronic banking in your organization.|  
    |**\($ T\_11306\_22 Notification E\-mail address $\)**|Specify the notification email address that you want to use for electronic banking balance and transaction messages. This is the default address that is used to contact the Isabel server.|  
    |**\($ T\_11306\_23 Language $\)**|Specify the language that you want to use for electronic bank balance and transaction messages.|  
    |**\($ T\_11306\_31 IBS Service Version $\)**|Specify the service version that is used to communicate with the Isabel server.|  
  
3.  On the **Upload** FastTab, fill in the fields as described in the following table. [!INCLUDE[bp_fieldhelp]()]  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11306\_24 Upload integration Mode $\)**|Specify the mode that you want to use to upload content to the Isabel server. The integration mode options include **Attended** and **Manual**. If the integration mode is set to **Attended**, you must set the **\($ T\_11306\_21 IBS Version $\)** field to **6**. The entries in the **\($ T\_2000010 IBS Log $\)** table will be created when payment files are generated. If the integration mode is set to **Manual**, you must log on to the Isabel server manually and no log entries will be created.|  
    |**\($ T\_11306\_25 Upload Path $\)**|Specify the path to the folder where the files will be saved during the upload process.|  
  
4.  On the **Download** FastTab, fill in the fields as described in the following table. [!INCLUDE[bp_fieldhelp]()]  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11306\_26 Download integration Mode $\)**|Specify the mode that you want to use to download content to the Isabel server. The options include **Attended** and **Manual**. If the integration mode is set to **Attended**, you must set the **\($ T\_11306\_21 IBS Version $\)** field to **6**. The entries in the **\($ T\_2000010 IBS Log $\)** table will be created when the download is performed. If the integration mode is set to **Manual**, you must log on to the Isabel server manually and no log entries will be created.|  
    |**\($ T\_11306\_27 Download Path $\)**|Specify the path to the folder where the files will be saved during the download process.|  
  
5.  On the **Numbering** FastTab, fill in the fields as described in the following table. [!INCLUDE[bp_fieldhelp]()]  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11306\_28 IBS Log Upload Nos. $\)**|Specify the number series that is used for Isabel log entries created during the file upload process.|  
    |**\($ T\_11306\_29 IBS Log Download Nos. $\)**|Specify the number series that is used for Isabel log entries created during the file download process.|  
    |**\($ T\_11306\_30 IBS Request ID $\)**|Specify a number sequence used for automatic and unique numbering of the requests.|  
  
6.  Choose the **OK** button.  
  
 Optionally, you can assign bank accounts to each customer and vendor. This helps make electronic payments simpler. The following procedure explains how to assign preferred bank accounts to customers, but the same steps also apply to vendors.  
  
### To add a preferred bank account to a customer  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Select a customer, and then choose **Edit**.  
  
3.  On the **Payments** FastTab, enter the **Preferred Bank Account**, and then choose the **OK** button.  
  
    > [!NOTE]  
    >  For all payments, use one bank account for each customer or vendor.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Isabel website](http://go.microsoft.com/fwlink/?LinkId=210323)   
 [Belgian Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-banking.md)   
 [Belgian Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-payments.md)   
 [How to: Set Up IBLC\-BLWI Transaction Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-iblc-blwi-transaction-codes.md)   
 [How to: Set Up Vendors for Automatic Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [How to: Generate Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-generate-payment-suggestions.md)   
 [How to: Create Payment Journal Templates and Batches](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-create-payment-journal-templates-and-batches.md)   
 [How to: Test Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-test-electronic-payments.md)   
 [How to: Manage Electronic Payment Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-manage-electronic-payment-lines.md)   
 [How to: Print Payment Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-print-payment-files.md)