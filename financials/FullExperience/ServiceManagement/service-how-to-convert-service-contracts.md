---
    title: How to: Convert Service Contracts | Microsoft Docs
    description: Because the VAT rate change tool cannot convert service contracts, these contracts must be converted manually. This topic describes several alternative methods that you can use for service contract conversion.
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
# How to: Convert Service Contracts
Because the VAT rate change tool cannot convert service contracts, these contracts must be converted manually. This topic describes several alternative methods that you can use for service contract conversion.  
  
> [!NOTE]  
>  This topic provides a high-level workflow.  
  
 The following procedure describes how to correct an invoice for a prepaid service contact that has been created a year in advance.  
  
> [!NOTE]  
>  For this example, you must change your work date to 01.01.2012.  
  
### To correct an invoice for a prepaid service contract  
  
1.  In the **Search** box, enter **Contract Management**, and then choose the related link.  
  
2.  Under **Lists**, choose **Service Contracts**.  
  
3.  Choose **New** to create a new prepaid service contract. Enter a start date of **01.01.2012** and an invoice period year for customer **20000**.  
  
4.  This contract must be signed. On the **Home** tab, in the **Process** group, choose **Sign Contract**.  
  
5.  Create a service invoice. On the **Home** tab, in the **Process** group, choose **Create Service Invoice**.  
  
6.  The invoice is listed as an unposted service invoice. To view the service invoice, choose **Service**, choose **Contract Management**, and then choose **Service Invoices**.  
  
7.  Post the service invoice.  
  
> [!NOTE]  
>  Do not change the unposted service invoice. Since the service ledger entries are created when the invoice is created, a change in the unposted invoice will not change the already created service ledger entries. However, the VAT entries are created when the invoice is posted. This lets you change the general product posting group and the GSP product posting group on the unposted service invoice.  
  
 The following procedure describes how to create a credit memo that only includes the VAT difference for the already invoiced period starting on **01.07.2012**. In this example, the VAT amount is only posted to the Financial Management module, not to the Service Management module. The VAT entries that are linked to the service ledger entry will not be corrected.  
  
### To create a credit memo for VAT difference  
  
1.  Create a new general ledger account for the VAT difference. This account will be used for direct posting of the VAT correction.  
  
2.  Add a new line to the VAT posting setup.  
  
 The following procedure describes how to create new contracts by working with contact expiration dates in service contract lines.  
  
### To create contract expiration dates in contract lines  
  
1.  In the **Service Contract** window, set the contract expiration date to **30.06.2012**.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Create Credit Memo** to automatically create a credit memo for July 2012 to December 2012.  
  
3.  Because the contract has expired, you need to create a new contract for the period with the new VAT rate for July 1, 2012 to December 31, 2012.  
  
 The following procedure describes how to create a new credit memo using the **Get Prepaid Contract Entries** batch job. Entries that you do not want to correct from January 2012 to June 2012 will be deleted.  
  
### To create a new credit memo  
  
1.  Run the VAT rate change tool on July 1, 2012. The general product posting group or the VAT product posting group is changed. For more information, see [How to: Perform VAT Rate Conversions](../how-to-perform-vat-rate-conversions.md).  
  
2.  After running the VAT rate change tool, enter a contract expiration date for the service contract. You can now delete the service contract line and create a new line that is identical to the old one.  
  
3.  Create a new invoice for the period of January 2012 to December 2012 using the new VAT rate.  
  
4.  To create another credit memo, in the **Service Credit Memos** window, choose **New** to create a new service credit memo.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Get Prepaid Contract Entries**.  
  
6.  After the conversion is complete, VAT and service ledger entries will be correct.  
  
## See Also  
 [How to: Perform VAT Rate Conversions](../how-to-perform-vat-rate-conversions.md)