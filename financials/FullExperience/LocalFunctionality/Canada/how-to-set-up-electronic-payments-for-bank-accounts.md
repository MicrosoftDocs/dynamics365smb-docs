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
# How to: Set Up Electronic Payments for Bank Accounts
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you can send electronic payments to vendors and electronic refunds to customers using the electronic payments function.  
  
 Electronic payments are exported in a standard United States or Canadian file format, and transmitted to the bank for processing. In the United States, this is done through the Automated Clearing House \(ACH\). In Canada, this is done through the Royal Bank.  
  
### To set up an electronic payment for a bank account  
  
1.  In the **Search** box, enter  **Bank Accounts**, and then choose the related link.  
  
2.  Select the required bank account. On the **Actions** tab, in the **Home** group, choose **Edit**.  
  
3.  On the **Transfer** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Export Format**|The country-specific file format for the export file. Choose the country\/region format that your bank uses.|  
    |**Payment Export Format**|The export file format when the format is not country-specific.<br /><br /> If this field is filled, then the **Export Format** field will be ignored. The payment file will be exported as set up in the **Payment Export Format** field. For more information, see [How to: Export Payments to a Bank File](../../BusinessFunctionality/DataExchange/how-to-export-payments-to-a-bank-file.md).|  
    |**E-Pay Export File Path**|The full directory path, starting with the drive letter and ending with a back slash \(\\\). You can enter a maximum of 80 characters.|  
    |**Last E-Pay Export File Name**|The file name without the path information. The file name should contain digits. The name will be incremented every time that it is exported, maintaining a permanent record of every file that you export to the bank. You can enter a maximum of 30 characters.|  
    |**Transit No.**|The bank transit number.|  
    |**Bank Account No.**|The bank account number.|  
    |**Bank Branch No.**|The bank branch number.|  
  
    > [!NOTE]  
    >  For Canadian export files, enter the information provided by the Royal Bank into the **Client No.**, **Client Name**, **Transit No.**, and **Input Qualifier** fields. For Mexican export files, enter the **SWIFT Code** \(international bank identifier code\) and the bank account's International Bank Account Number \(IBAN\) into the **SWIFT Code** and **IBAN** fields.  
  
4.  On the **Posting** FastTab, in the **Last Remittance Advice No.** field, enter the last remittance advice number.  
  
    > [!NOTE]  
    >  Instead of using check stock to print remittance advice for employees who are not receiving a paycheck, you can print remittance advice using blank paper. If you use this option, you must use a different number series so that they are not confused with your check numbers. We recommend that you use letters in the number series, so that you can easily identify these as non-checks. For example – RA00000. You can enter a maximum of 20 characters.  
  
5.  Create a directory on your computer for the transmission program path.  
  
6.  Choose the **OK** button.  
  
### To set up an electronic payment for a vendor bank account  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link in **Payables**.  
  
2.  Select the vendor for which you want to set up electronic payments.  
  
3.  On the **Navigate** tab, in the **Vendor** group, choose **Bank Accounts**.  
  
4.  Select the vendor bank account.  
  
5.  On the **Home** tab, in the **Manage** group, choose **Edit**. The **Vendor Bank Account Card** opens.  
  
6.  On the **General** FastTab, select the **Use for Electronic Payments** check box.  
  
7.  Choose the **OK** button.  
  
## See Also  
 [How to: Generate Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-generate-electronic-payments.md)   
 [How to: Void Posted Checks](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-void-posted-checks.md)