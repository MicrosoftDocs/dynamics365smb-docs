---
title: "How to: Set Up Sales VAT Advance Notifications for ELSTER"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales VAT advance notifications, setting up"
  - "ELSTER, setting up notifications"
  - "sales VAT advance notifications, ELSTER"
  - "VAT, setting up for ELSTER"
ms.assetid: ee22a9d6-c200-48d2-b473-4fe1c6867fc6
caps.latest.revision: 40
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Set Up Sales VAT Advance Notifications for ELSTER
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], to submit valid sales VAT advance notifications to the ELSTER portal, you must set up the following:  
  
-   The company registration information and tax office information.  
  
-   The number series for sales VAT advance notification.  
  
-   The user authentication for the tax authorities.  
  
-   The VAT statement.  
  
 You must also download components from the ELSTER portal. For more information, see the [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998).  
  
### To set up company information  
  
1.  In the **Search** box, enter **\($ N\_1 Company Information $\)**, and then choose the related link.  
  
2.  In the **\($ N\_1 Company Information $\)** window, on the **General** FastTab, in the **\($ T\_79\_11019 VAT Representative $\)** field, enter the contact person for VAT related information.  
  
3.  On the **Tax Office** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_79\_11103 Tax Office Number $\)**|The tax office number. You can ask your tax office for this number.|  
    |**\($ T\_79\_20 Registration No. $\)**|The company's registration number.<br /><br /> You can enter a maximum of 20 alphanumeric characters.|  
  
 For more information, see [How to: Enter Company Information](../../Finance/how-to-enter-company-information.md) and [\($ N\_1 Company Information $\)](assetId:///45c9cfb7-ca1f-4323-99cd-9360a5631648).  
  
### To set up the number series for sales VAT advance notifications  
  
1.  In the **Search** box, enter **\($ N\_118 General Ledger Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_118 General Ledger Setup $\)** window, on the **Numbering** FastTab, in the **\($ T\_98\_11011 Sales VAT Advance Notif. Nos. $\)** field, select the number series code for the sales VAT advance notifications.  
  
 For more information, see [\($ N\_118 General Ledger Setup $\)](assetId:///40b9235c-b0d7-4a9f-9ecf-6dc97655309b).  
  
### To set up user authentication for ELSTER  
  
1.  In the **Search** box, enter **\($ N\_11019 Electronic VAT Decl. Setup $\)**, and then choose the related link.  
  
2.  To submit signed data to the tax authorities, on the **General** FastTab, select the **\($ T\_11013\_2 Use Authentication $\)** field.  
  
    > [!CAUTION]  
    >  If your company has submitted signed data in a previous period, the tax authorities will only accept signed data.  
  
3.  Optionally, on the **Communication** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11013\_5 Use Proxy Server $\)**|Select to use a proxy server for communication.|  
    |**\($ T\_11013\_6 Proxy Server Authent. Required $\)**|Select to use a dedicated proxy server for authentication.<br /><br /> If you use a proxy server and the required dedicated authentication, then you must enter the user account and the password before transmitting. If you use Windows authentication, do not select this field.|  
    |**\($ T\_11013\_7 Proxy Server IP\-Address\/Port $\)**|The address and the port that will be used for communication if you use a proxy server.|  
  
4.  On the **HTTP Servers** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11013\_8 HTTP Server URL 1 $\)**|Specifies a server of the Oberfinanzdirektion \(OFD\), such as **http:\/\/datenannahme1.elster.de\/Elster2\/EMS**.|  
    |**\($ T\_11013\_9 HTTP Server URL 2 $\)**|Specifies a server of the OFD, such as **http:\/\/datenannahme2.elster.de\/Elster2\/EMS**.|  
    |**\($ T\_11013\_10 HTTP Server URL 3 $\)**|Specifies a server of the OFD, such as **http:\/\/datenannahme3.elster.de\/Elster2\/EMS**.|  
    |**\($ T\_11013\_10 HTTP Server URL 4 $\)**|Specifies a server of the OFD, such as **http:\/\/datenannahme4.elster.de\/Elster2\/EMS**.|  
  
     Now you must specify the users who can submit documents to the ELSTER portal.  
  
5.  On the **Navigate** tab, choose **Certificates**.  
  
     For more information about ELSTER certificates, see the [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998).  
  
    1.  In the **\($ N\_11020 Certificates $\)** window, in the **\($ T\_11014\_1 User ID $\)** field, specify the user who you want to authorize to submit documents to ELSTER.  
  
    2.  On the **Actions** tab, choose **Upload Elster Certificate**, and then specify the certificate file, such as Coala2019.pem.cer.  
  
    3.  Choose **Upload PFX File**, and then specify the personal certificate file for this user, such as test\-soft\-pse.pfx.  
  
        > [!IMPORTANT]  
        >  If data encryption is not already enabled, you must enable it before you proceed. For more information, see [\($ N\_9905 Data Encryption Management $\)](../Topic/\($%20N_9905%20Data%20Encryption%20Management%20$\).md).  
  
    4.  Choose **Set Pfx File Password**, and then specify the password for this personal certificate.  
  
6.  Repeat step 5 for other users who will submit documents to ELSTER.  
  
7.  Choose the **OK** button.  
  
### To set up a VAT statement for sales VAT advance notifications  
  
1.  In the **Search** box, enter **\($ N\_317 VAT Statement $\)**, and then choose the related link.  
  
2.  In the **\($ N\_317 VAT Statement $\)** window, in the **\($ N\_317\_35 Name $\)** field, choose the drop\-down arrow.  
  
3.  In the **\($ N\_320 VAT Statement Names $\)** window, in the line for the appropriate VAT statement name select the **\($ T\_257\_11000 Sales VAT Adv. Notification $\)** field.  
  
    > [!NOTE]  
    >  Only one VAT statement name can be selected for sales VAT advance notification at one time. The VAT statement must have a VAT statement line for each key figure required by the tax authority, where the **\($ T\_256\_4 Row No. $\)** field contains the key figure and the **\($ T\_256\_12 Amount Type $\)** field specifies if this is a base amount or a tax amount. Ask your tax office if you have questions concerning the key figures and their definition.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [\($ T\_257\_11000 Sales VAT Adv. Notification $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/-$-t_257_11000-sales-vat-adv.-notification-$-.md)   
 [\($ T\_256 VAT Statement Line $\)](assetId:///827c23e2-cae1-492e-9b90-68b5c3418236)   
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 [How to: Create and Submit Sales VAT Advance Notifications](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-create-and-submit-sales-vat-advance-notifications.md)   
 [How to: Enter Company Information](../../Finance/how-to-enter-company-information.md)   
 [\($ T\_79 Company Information $\)](assetId:///2a44e662-0d42-429e-8131-e0012a89996a)   
 [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6)