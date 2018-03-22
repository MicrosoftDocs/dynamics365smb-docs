---
    title: How to Set Up Electronic Banking
    description: With electronic banking, you can make electronic payments to domestic, international, SEPA, and non-Euro SEPA vendors and customers.

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
# Set Up Electronic Banking
> [!Note]
> [!INCLUDE[onprem_only](../../includes/onprem_only_md.md)]

With electronic banking, you can make electronic payments to domestic, international, SEPA, and non-Euro SEPA vendors and customers.  

Your company subscribes to an eBanking contract with the bank to maintain a certain bank account or several bank accounts. The company also subscribes to Isabel to send payment files to and receive bank statement files from the bank electronically. Therefore, the company receives smartcards linked to the eBanking contract. The smartcards are secured by PIN codes.  

You will receive one of these smartcards to connect to IBS so that you are connected to the eBanking contract of the company.  

When uploading to or downloading files from the IBS platform, you will insert the smartcard in the card reader and use a PIN code to make connection to IBS. When the IBS session is established, the eBanking contract and eBanking user is known by the system. Also the eBanking contract and user linked bank account numbers are known.  

Before you can use electronic banking, you must set up the following information:  

- Electronic banking setup.  
- IBLC/BLWI codes - For more information, see [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md).  

## To set up electronic banking  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Electronic Banking Setup**, and then choose the related link.  
2.  In the **Electronic Banking Setup** window, on the **General** FastTab, fill in the fields as described in the following table.   

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Summarize Gen. Jnl. Lines**|Select to indicate if you want to group the payment journal lines for each vendor.|  
    |**Cut off Payment Message Texts**|Select to indicate if you want to truncate long payment messages. Messages will be truncated if greater than 106 characters for domestic payments and less than 140 characters for international payments.|  
    |**IBS Version**|Specify the version of Isabel that is currently used for electronic banking in your organization.|  
    |**Notification E-mail address**|Specify the notification email address that you want to use for electronic banking balance and transaction messages. This is the default address that is used to contact the Isabel server.|  
    |**Language**|Specify the language that you want to use for electronic bank balance and transaction messages.|  
    |**IBS Service Version**|Specify the service version that is used to communicate with the Isabel server.|  

3.  On the **Upload** FastTab, fill in the fields as described in the following table.   

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Upload integration Mode**|Specify the mode that you want to use to upload content to the Isabel server. The integration mode options include **Attended** and **Manual**. If the integration mode is set to **Attended**, you must set the **IBS Version** field to **6**. The entries in the **IBS Log** table will be created when payment files are generated. If the integration mode is set to **Manual**, you must log on to the Isabel server manually and no log entries will be created.|  
    |**Upload Path**|Specify the path to the folder where the files will be saved during the upload process.|  

4.  On the **Download** FastTab, fill in the fields as described in the following table.   

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Download integration Mode**|Specify the mode that you want to use to download content to the Isabel server. The options include **Attended** and **Manual**. If the integration mode is set to **Attended**, you must set the **IBS Version** field to **6**. The entries in the **IBS Log** table will be created when the download is performed. If the integration mode is set to **Manual**, you must log on to the Isabel server manually and no log entries will be created.|  
    |**Download Path**|Specify the path to the folder where the files will be saved during the download process.|  

5.  On the **Numbering** FastTab, fill in the fields as described in the following table.   

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**IBS Log Upload Nos.**|Specify the number series that is used for Isabel log entries created during the file upload process.|  
    |**IBS Log Download Nos.**|Specify the number series that is used for Isabel log entries created during the file download process.|  
    |**IBS Request ID**|Specify a number sequence used for automatic and unique numbering of the requests.|  

6.  Choose the **OK** button.  

## See Also  
 [Isabel website](http://go.microsoft.com/fwlink/?LinkId=210323)   
 [Belgian Electronic Banking](belgian-electronic-banking.md)   
 [Belgian Electronic Payments](belgian-electronic-payments.md)   
 [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)   
 [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [Generate Payment Suggestions](how-to-generate-payment-suggestions.md)   
 [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
 [Test Electronic Payments](how-to-test-electronic-payments.md)   
 [Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md)   
 [Print Payment Files](how-to-print-payment-files.md)
 [Summarizing Payment Lines and General Journal Lines](summarizing-payment-lines-and-general-journal-lines.md)
 