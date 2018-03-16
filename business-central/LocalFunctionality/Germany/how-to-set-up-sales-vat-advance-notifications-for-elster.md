---
    title: How to Set Up Sales VAT Advance Notifications for ELSTER
    description: In Business Central, to submit valid sales VAT advance notifications to the ELSTER portal, you must perform certain setup.

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
# Set Up Sales VAT Advance Notifications for ELSTER
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], to submit valid sales VAT advance notifications to the ELSTER portal, you must set up the following:  

- The company registration information and tax office information.  
- The number series for sales VAT advance notification.  
- The user authentication for the tax authorities.  
- The VAT statement.  

You must also download components from the ELSTER portal. For more information, see the [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998).  

## To set up company information  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.  
2.  In the **Company Information** window, on the **General** FastTab, in the **VAT Representative** field, enter the contact person for VAT related information.  
3.  On the **Tax Office** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Use Proxy Server**|Select to use a proxy server for communication.|  
    |**Proxy Server Authent. Required**|Select to use a dedicated proxy server for authentication.<br /><br /> If you use a proxy server and the required dedicated authentication, then you must enter the user account and the password before transmitting. If you use Windows authentication, do not select this field.|  
    |**Proxy Server IP-Address/Port**|The address and the port that will be used for communication if you use a proxy server.|  

4.  On the **HTTP Servers** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**HTTP Server URL 1**|Specifies a server of the Oberfinanzdirektion (OFD), such as **http://datenannahme1.elster.de/Elster2/EMS**.|  
    |**HTTP Server URL 2**|Specifies a server of the OFD, such as **http://datenannahme2.elster.de/Elster2/EMS**.|  
    |**HTTP Server URL 3**|Specifies a server of the OFD, such as **http://datenannahme3.elster.de/Elster2/EMS**.|  
    |**HTTP Server URL 4**|Specifies a server of the OFD, such as **http://datenannahme4.elster.de/Elster2/EMS**.|  

    Now you must specify the users who can submit documents to the ELSTER portal.  

5.  Choose the **Certificates** action.  

    For more information about ELSTER certificates, see the [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998).  

    1.  In the **Certificates** window, in the **User ID** field, specify the user who you want to authorize to submit documents to ELSTER.  
    2.  Choose the **Upload Elster Certificate** action, and then specify the certificate file, such as Coala2019.pem.cer.  
    3.  Choose **Upload PFX File**, and then specify the personal certificate file for this user, such as test-soft-pse.pfx.  

        > [!IMPORTANT]  
        >  If data encryption is not already enabled, you must enable it before you proceed.

    4.  Choose the **Set Pfx File Password** option, and then specify the password for this personal certificate.  

6.  Repeat step 5 for other users who will submit documents to ELSTER.  
7.  Choose the **OK** button.  

## To set up a VAT statement for sales VAT advance notifications  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Statement**, and then choose the related link.  
2.  In the **VAT Statement** window, in the **Name** field, choose the drop-down arrow.  
3.  In the **VAT Statement Names** window, in the line for the appropriate VAT statement name select the **Sales VAT Adv. Notification** field.  

    > [!NOTE]  
    >  Only one VAT statement name can be selected for sales VAT advance notification at one time. The VAT statement must have a VAT statement line for each key figure required by the tax authority, where the **Row No.** field contains the key figure and the **Amount Type** field specifies if this is a base amount or a tax amount. Ask your tax office if you have questions concerning the key figures and their definition.  

4.  Choose the **OK** button.  

## See Also  
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 [Create and Submit Sales VAT Advance Notifications](how-to-create-and-submit-sales-vat-advance-notifications.md)
