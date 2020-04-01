---
    title: How to Set Up Export Protocols
    description: Before you can use electronic banking, you must set up export protocols. Export protocols define the file format that is generated when you export payment history to be processed by the bank. Each line contains an export protocol identified by a code and a description. You can set up as many export protocols as necessary. You must set up an export protocol for domestic payments, international payments, SEPA payments, and non-Euro SEPA payments.

    services: project-madeira 
    documentationcenter: ''
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
# Set Up Export Protocols
Before you can use electronic banking, you must set up export protocols. Export protocols define the file format that is generated when you export payment history to be processed by the bank. Each line contains an export protocol identified by a code and a description. You can set up as many export protocols as necessary. You must set up an export protocol for domestic payments, international payments, SEPA payments, and non-Euro SEPA payments.  

 With export protocols, you can assign the codeunit that defines the check that should be performed before exporting the payment lines to a file and the report that defines the payment format. For example, you might have an export protocol named **DOM1**. This export protocol contains the **Check Domestic Payments** check codeunit and the **File Domestic Payments** report. Each export protocol has both a check codeunit and a matching report, as shown in the following table.  

|**Check Object ID**|**Export Object ID**|  
|-------------------------|--------------------------|  
|2000002 Check Domestic Payments|Report 2000001 File Domestic Payments|  
|2000003 Check International Payments|Report 2000002 File International Payments|  
|2000004 Check SEPA Payments|Report 2000005 File SEPA Payments|  
|2000005 Check Non Euro SEPA Payments|Report 2000006 File Non Euro SEPA Payments|  
|If you do not want this option, set it to zero; otherwise, select another option.|XMLport 1000 (SEPA pain.001.001.03 Payments)|  

 After you have set up export protocols, you can use them in your electronic banking payment journals.  

## To set up an export protocol  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export Protocols**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **Export Protocols**  page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify a code that uniquely identifies the export protocol.|  
    |**Description**|Specify a description for the export protocol entry. You can enter a maximum of 50 characters, both numbers and letters.|  
    |**Code Expenses**|Specify the code that describes the type of expenses associated with the export protocol entry. Code expenses include **blank**, **SHA**, **BEN**, and **OUR**. For international payments, **SHA** is the default.|  
    |**Check Object ID**|Specify the identification number of the codeunit that you want to use to perform a check on the object before the payment file is exported.|  
    |**Check Object Name**|Specify the name of a verification process that is used to perform a check on the object before the payment file is exported. After you select the **Check Object ID**, this field will display the **Check Object Name**.|  
    |**Export Object Type**|Specify the type of the object that defines the export format of the payment file export. After you select the **Export Object ID**, this field will display the **Export Object Type**.<br /><br /> **NOTE:** To set the export protocol up for SEPA pain.001.001.03, select **XMLPort**.|  
    |**Export Object ID**|Specify the identification number of the object that defines the export format of the payment file export. For example, if you select **2000002**, the export format for the payment file will be **File International Payments**.<br /><br /> **NOTE:** To set up the export protocol for SEPA pain.001.001.03, select XMLport **1000**.|  
    |**Export No. Series**|Specify the number series that is used to assign identification numbers to the payment file export.|  

4.  Choose the **OK** button.  

## See Also  
 [Belgian Electronic Payments](belgian-electronic-payments.md)   
 [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
 [Test Electronic Payments](how-to-test-electronic-payments.md)
