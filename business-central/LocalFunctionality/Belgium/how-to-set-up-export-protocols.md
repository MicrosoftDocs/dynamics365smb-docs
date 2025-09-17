---
title: How to set up export protocols [BE]
description: Set up export protocols to define the file format for export payment history before using electronic banking.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: export protocols, define file format, export payment history, electronic banking, Belgian version
ms.search.form: 2000005
ms.date: 04/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up export protocols in the Belgian version

Before you can use electronic banking, you must set up export protocols. Export protocols define the file format that is generated when you export payment history to be processed by the bank. Each line contains an export protocol identified by a code and a description. You can set up as many export protocols as necessary. You must set up an export protocol for domestic payments, international payments, SEPA payments, and non-Euro SEPA payments.  

 With export protocols, you can assign the codeunit that defines the check that should be performed before exporting the payment lines to a file and the report that defines the payment format. For example, you might have an export protocol named **DOM1**. This export protocol contains the **Check Domestic Payments** check codeunit and the **File Domestic Payments** report. Each export protocol has both a check codeunit and a matching report, as shown in the following table.  

|**Check Object ID**|**Export Object ID**|  
|-------------------------|--------------------------|  
|2000002 Check Domestic Payments|Report 2000001 File Domestic Payments|  
|2000003 Check International Payments|Report 2000002 File International Payments|  
|2000004 Check SEPA Payments|Report 2000005 File SEPA Payments|  
|2000005 Check Non-Euro SEPA Payments|Report 2000006 File Non-Euro SEPA Payments|  
|2000007 Check SEPA 001.001.09 Payments|Report 2000008 File FCY SEPA 001.001.09 Payments|
|If you don't want this option, set it to zero; otherwise, select another option.|XMLport 1000 (SEPA pain.001.001.03 Payments)|  

 After you set up export protocols, you can use them in your electronic banking payment journals.  

## Setup process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Export Protocols**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **Export Protocols**  page, fill in the fields as described in the following table.  

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Code**|Specify a code that uniquely identifies the export protocol.|  
   |**Description**|Specify a description for the export protocol entry. You can enter a maximum of 50 characters, both numbers and letters.|  
   |**Code Expenses**|Specify the code that describes the type of expenses associated with the export protocol entry. Code expenses include **blank**, **SHA**, **BEN**, and **OUR**. For international payments, **SHA** is the default.|  
   |**Check Object ID**|Specify the identification number of the codeunit that you want to use to perform a check on the object before the payment file is exported.|  
   |**Check Object Name**|Specify the name of a verification process that is used to perform a check on the object before the payment file is exported. After you select the **Check Object ID**, this field will display the **Check Object Name**.|  
   |**Export Object Type**|Specify the type of the object that defines the export format of the payment file export. After you select the **Export Object ID**, this field displays the **Export Object Type**.<br><br/> **NOTE:** To set up the export protocol for SEPA pain.001.001.03, select **XMLPort**.|  
   |**Export Object ID**|Specify the identification number of the object that defines the export format of the payment file export. For example, if you select **2000002**, the export format for the payment file is **File International Payments**.<br><br/> **NOTE:** To set up the export protocol for SEPA pain.001.001.03, select XMLport **1000**.|  
   |**Export No. Series**|Specify the number series that is used to assign identification numbers to the payment file export.|  
   |**Grouped Payment**|Specifies if this export protocol is used for grouped payments.|  

1. Choose the **OK** button.  

## Related information

- [Belgian Electronic Payments](belgian-electronic-payments.md)   
- [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
- [Test Electronic Payments](how-to-test-electronic-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
