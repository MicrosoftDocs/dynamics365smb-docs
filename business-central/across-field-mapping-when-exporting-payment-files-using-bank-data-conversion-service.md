---
    title: Field mapping for exporting bank payment files | Microsoft Docs
    description: When you export payment files using the AMC Banking 365 Fundamentals extension, the data that you export is exposed to the service provider.
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
# Field Mapping When Exporting Payment Files Using the AMC Banking 365 Fundamentals extension
When you export payment files using the AMC Banking 365 Fundamentals extension, the data that you export is exposed to the service provider. The service provider is responsible for the privacy of this data. For more information about the AMC Banking 365 Fundamentals extension, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md).  

> [!CAUTION]  
>  When you export payment files by using the AMC Banking 365 Fundamentals extension, some of your business data will be exposed to the provider of the service. The service provider, AMC Consult A/S, is responsible for the privacy of this data. For more information, see [AMC Privacy Policy](https://go.microsoft.com/fwlink/?LinkId=510158).  

The following table lists the fields in [!INCLUDE[d365fin](includes/d365fin_md.md)] from which you can export data.  

|Mapped Field|Field in Table|Table|Description|  
|------------------|--------------------|-----------|---------------------------------------|  
|Creditor No.|Creditor No.|Bank Account|The identifier assigned to your company by your bank to collect payments|  
|Sender Bank Account No.|Bank Account No./IBAN|Bank Account|Your company's bank account number (IBAN or other) that is specified on the bank account card|  
|Sender Bank Clearing Standard|Bank Clearing Standard|Bank Account|The national bank names register used for the sender bank account|  
|Sender Bank Clearing Code|Bank Clearing Code|Bank Account|The identifier of the sender's bank in relation to the bank names register used|  
|Sender Bank BIC|SWIFT Code|Bank Account|The SWIFT identifier of the sender bank account|  
|Sender Bank Account Currency|Currency Code|Bank Account|The sender bank account Currency Code|  
|Document No.|Document No.|General Journal Line|The document number of the payment line|  
|Applies-to Ext. Doc. No.|Applies-to Ext. Doc. No.|General Journal Line|The external document number of the invoice or credit memo that the payment line is applied to|  
|Recipient ID|Account No.|General Journal Line|The customer or vendor number that is specified on the payment line|  
|Payment Type|Bank Data Conversion Pmt. Type|Payment Method|The type of bank transfer, such as domestic or international|  
|Payment Reference|Payment Reference|General Journal Line|The payment reference of the payment line|  
|Recipient Address|Address|Customer/Vendor|The recipient address that is specified on the customer or vendor card|  
|Recipient City|City|Customer/Vendor|The recipient city that is specified on the customer or vendor card|  
|Recipient Name|Name|Customer/Vendor|The recipient name that is specified on the customer or vendor card|  
|Recipient Country/Region Code|Country/Region Code|Customer/Vendor|The recipient country/region code that is specified on the customer or vendor card|  
|Recipient Post Code|Post Code|Customer/Vendor|The recipient post code that is specified on the customer or vendor card|  
|Recipient Bank Acc. No.|Bank Account No./IBAN|Customer Bank Account/Vendor Bank Account|The recipient bank account number (IBAN or other) that is specified on the customer or vendor bank account card|  
|Recipient Bank Clearing Code|Bank Clearing Standard|Customer Bank Account/Vendor Bank Account|The national bank names register used for the recipient bank account|  
|Recipient Bank Clearing Std.|Bank Clearing Code|Customer Bank Account/Vendor Bank Account|The identifier of the recipient bank account in relation to the bank names register that is used|  
|Recipient Email Address|E-Mail|Customer/Vendor|The email address of the recipient|  
|Message To Recipient 1|Message to Recipient|General Journal Line|The message to recipient that is specified on the payment line|  
|Amount|Amount|General Journal Line|The amount on the payment line|  
|Currency Code|Currency Code|General Journal Line|The currency code on the payment line|  
|Transfer Date|Posting Date|General Journal Line|The posting date of the payment line|  
|Invoice Amount|Original Amount|Customer/Vendor Ledger Entry|The amount on the entry that the payment is applied to|  
|Invoice Date|Document Date|Customer/Vendor Ledger Entry|The invoice date on the entry that the payment is applied to|  
|Recipient Bank Address|Address|Customer Bank Account/Vendor Bank Account|The recipient bank account address that is specified on the customer or vendor bank account card|  
|The recipient bank account address that is specified on the customer or vendor bank account card|City|Customer Bank Account/Vendor Bank Account|The recipient bank account city that is specified on the customer or vendor bank account card|  
|Recipient Bank Name|Name|Customer Bank Account/Vendor Bank Account|The recipient bank account name that is specified on the customer or vendor bank account card|  
|Recipient Bank Country/Region|Country/Region Code|Customer Bank Account/Vendor Bank Account|The recipient bank account country/region that is specified on the customer or vendor bank account card|  
|Recipient Bank Post Code|Post Code|Customer Bank Account/Vendor Bank Account|The recipient bank account post code that is specified on the customer or vendor bank account card|  
|Sender Bank Address|Address|Bank Account|The sender bank account address that is specified on the bank account card|  
|Sender Bank City|City|Bank Account|The sender bank account city that is specified on the bank account card|  
|Sender Bank Name|Name|Bank Account|The sender bank account name that is specified on the bank account card|  
|Sender Bank Country/Region|Country/Region Code|Bank Account|The sender bank account country/region that is specified on the bank account card|  
|Sender Bank Post Code|Post Code|Bank Account|The sender bank account post code that is specified on the bank account card|  
|General Journal Template|Journal Template Name|General Journal Line|The general journal template that is used for the payment line|  
|General Journal Batch Name|Journal Batch Name|General Journal Line|The general journal batch name that is used for the payment line|  
|Sender Bank Name - Data Conv.|Bank Name – Data Conv.|Bank Account|The sender bank account name that is requested by the AMC Banking 365 Fundamentals extension and specified on the bank account card|  

## See Also  
[Setting Up Data Exchange](across-set-up-data-exchange.md)  
[Exchanging Data Electronically](across-data-exchange.md)
[Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md)   
[Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)   
