---
title: "How to: Prepare for VAT Transactions Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT reports, setting up"
  - "VAT, setting up transactions reports"
ms.assetid: 79d810ad-ae88-4e01-99af-d48923f4ae8f
caps.latest.revision: 20
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Prepare for VAT Transactions Reports
You must submit periodic reports to the tax authorities to list all transactions that include VAT. The tax authority establishes the thresholds at which reporting is required. Currently, the threshold is set at zero, meaning that all transactions are to be reported. To prepare for these reports, you must set up VAT posting to include VAT transaction report amounts.  
  
### To set up VAT transaction amounts  
  
1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  On the **Navigate** tab, choose **VAT Transaction Report Amount**.  
  
3.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Specifies the start date for this threshold, such as 01.05.2011.<br /><br /> Transactions that are posted on or after this date are included in the calculations for the VAT transaction report.|  
    |**Threshold Amount Excl. VAT**|Specifies the minimum base amount that will be included in the VAT transaction report.<br /><br /> This amount is determined by the requirements from the tax authorities.|  
    |**Threshold Amount Incl. VAT**|Specifies the minimum amount including VAT that will be included in the VAT transaction report.|  
  
4.  Choose the **OK** button.  
  
 You must also configure each VAT posting setup that is used for transactions that are included in the VAT transaction report.  
  
 The initial setting of the **Include in VAT Transac. Report** check box is based your VAT posting setup, the customer and vendor country\/region, and the specific line, but you can override the setting of the check box in sales, purchase, service, and general journal lines that are posted to VAT entries. If [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] does not permit the changed setting, an error will be displayed during posting.  
  
### To set up VAT posting for VAT transaction reporting  
  
1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  Select the VAT posting setup that must be enabled for VAT transaction reporting. Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Include in VAT Transac. Rep.**|Select to include transactions that use this VAT posting setup in the VAT transaction report.|  
  
     Italian legislation provides a list of transactions that are exempt from VAT transaction reporting, such as financial transactions, insurance, and so on. If a line must be excluded from the VAT transaction reports, you can clear the Include in VAT Transac. Rep. check box for that line.  
  
 When a transaction such as posting a sales invoice is made that uses this VAT posting setup, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] checks if the transaction meets the threshold amounts. The check is based on document lines because a document can contain lines that must be included in the VAT transaction report and lines that must be excluded. The VAT transaction reports must only contain the lines that must be submitted, so [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] compares amounts against the threshold for each line rather than for a document.  
  
 Next, if you have a representative, you can set up appointment code information in the **Appointment Code** window.  
  
 In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can provide information about appointment codes, which are used in many types of VAT transaction reports. The codes are defined by the Italian tax authority, and are used to describe who is submitting the report on your behalf. Reports that use appointment codes include:  
  
-   Annual VAT Communication  
  
-   Exp. Annual VAT Comm.  
  
-   Blacklist Communication  
  
 You set up the code information once, and then can use it in the various reports. For example, you enter the code 1 if there is a legal representative or managing partner.  
  
### To set up appointment codes  
  
1.  In the **Search** box, enter **Appointment Codes**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Manage** group, choose **Edit List**.  
  
3.  On a new line, specify a code and description of the Appointment code. For more information, see the instructions on the Agenzia Entrate website.  
  
4.  Choose the **OK** button.  
  
 Next, proceed to the **VAT Report Setup** window to set up information about intermediaries and Spesometro appointments. After you complete the setup, you are ready to create and submit VAT transactions reports or blacklist communication reports.  
  
### To set up VAT reports  
  
1.  In the **Search** box, enter **VAT Report Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, select the **Modify Submitted Reports** field to let users modify VAT reports that have been submitted to the tax authorities.  
  
     If the field is left blank, users must create a corrective VAT report instead.  
  
    > [!NOTE]  
    >  In Italy, the tax authorities require that you use corrective VAT reports and that you do not modify submitted reports.  
  
3.  On the **Numbering** FastTab, specify the number series that will be used for standard VAT reports.  
  
     Depending on the requirements, you can use the same number series for all VAT reports, or separate number series for each type of VAT report. For more information, see No. Series.  
  
     For example, if your company uses separate number series for standard and corrective VAT reports, this number series is the default number series. Users can select a different number series in the **No.** field if they create corrective reports.  
  
4.  On the **Intermediary** FastTab, enter information about the intermediary, such as the VAT Registration No. of the person or entity performing the report transmission. This information is used in the VAT report in the place of the company's information when [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] specifies the type of declarer.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Intermediary VAT Registration No.**|Specify the VAT registration number of intermediary.<br /><br /> If you have a tax representative, you must fill in the field by using the VAT registration number or the fiscal code for the tax representative. You can find this information based on the value of the Tax Representative No. field in the **Company Information** window.|  
    |**Intermediary CAF Registration No.**|Specify the CAF registration number of your tax assistance center.|  
    |**Intermediary Date**|Specify the date that you entered into the agreement with the external party.<br /><br /> You are required to fill in this field if the **Intermediary CAF Reg. No.** field is filled in.|  
  
5.  If you have a representative, on the **Spesometro Appointments** FastTab, fill in the fields as described in the following table.  
  
    > [!NOTE]  
    >  If you do not have an appointment, but do have a tax representative, in the report Microsoft Dynamics NAV creates the appointment based on the tax representative information in the Company Information window. In that case, the Starting Date is the start date of the report. There is no Ending Date.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Appointment Code.**|Specify the code for the Spesometro appointment. You can select a code from the list that you set up in the **Appointment Codes** window.|  
    |**Vendor No.**|Required. Enter the number of the vendor doing the appointment work.|  
    |**Starting Date**|Specify the date of the start of the appointment.<br /><br /> If the time period covered by the data transmission is outside of the appointment start date, then information about the appointment is ignored. In that case, Microsoft Dynamics NAV will use the information about your tax representative, if that is available.|  
    |**Ending Date Date**|Optional. Specify the date of the end of the appointment. If no end date is specified, the appointment is ongoing.|  
    |**Designation**|Enter text to describe the role of the appointment. You fill in this field in the case that the Spesometro appointment is not an individual person.|  
  
## Updating Customers and Vendors  
 According to the requirements of the tax authorities, you must specify if a customer or vendor is an individual person, and if the person is a resident of Italy.  
  
> [!NOTE]  
>  The following sections describe how to modify a customer, but the same steps apply to vendors.  
  
#### To specify a customer as an individual person  
  
1.  In the **Search** box, enter **Customer Card**, and then choose the related link.  
  
2.  On the **Individual** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Individual Person**|Select if this customer is an individual person.|  
    |**Resident**|Specify if the customer is a resident in Italy.<br /><br /> If a customer is not a resident, you must also specify a tax representative on the **Foreign Trade** FastTab.|  
    |**First Name**|Specifies the first name of the person.|  
    |**Last Name**|Specifies the last name of the person.|  
    |**Date of Birth**|Specifies the date of birth of the person.|  
    |**Place of Birth**|Specifies the place of birth of the person.|  
  
3.  If the customer is not resident in Italy and is not an individual person, you must specify a tax representative for the customer.  
  
    > [!NOTE]  
    >  Before you can specify a tax representative, you must have created the tax representative as a contact.  
  
#### To specify a tax representative for a non\-resident customer  
  
1.  In the **Search** box, enter **Customer Card**, and then choose the related link.  
  
2.  On the **Foreign Trade** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Tax Representative Type**|Specifies if the tax representative is a customer or a contact. You must set this field to **Contact**.|  
    |**Tax Representative No.**|Specify the contact that is the tax representative for this customer.|  
  
 You have set up information so that [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] will track new transactions with VAT that meet the thresholds that are specified by the tax authorities. Before you create the first VAT transaction report, you should prepare the existing data. For more information, see [How to: Update VAT Transactions Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-update-vat-transactions-data.md). You can then create VAT transactions reports. For more information, see [How to: Create Electronic VAT Transactions Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-create-electronic-vat-transactions-reports.md).  
  
## See Also  
 [How to: Update VAT Transactions Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-update-vat-transactions-data.md)   
 [How to: Create Electronic VAT Transactions Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-create-electronic-vat-transactions-reports.md)   
 [Italian VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/italian-vat.md)   
 VAT Report Setup