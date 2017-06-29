---
title: "How to: Set Up Document Sending Profiles"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 403ef908-9c1e-4c20-b3c7-da0edf9bff85
caps.latest.revision: 15
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up Document Sending Profiles
You can set each customer up with a preferred method of sending sales documents, so that you do not have to select a sending option every time you choose the **Post and Send** button.  
  
 In the **Document Sending Profiles** window, you set up different sending profiles that you can select from in the **Document Sending Profile** field on a customer card. In the **Document Sending Profile** window for a sending profile, you can select the **Default** check box to specify that the document sending profile is the default profile for all customers, except for customers where the **Document Sending Profile** field is filled with another sending profile.  
  
 When you choose the **Post and Send** button on a sales document, the **Post and Send Confirmation** dialog box shows the sending profile used, either the one set up for the customer or the default for all customers. In the dialog box, you can change the sending profile for the sales document. For more information, see [How to: Invoice Sales](../Finance/how-to-invoice-sales.md).  
  
 One of the options that you can choose for a sending profile is **Send Electronically**. This option means that the document is sent as a standard\-compliant file representing the document record, such as a sales invoice, which can be imported into the recipient’s system as a purchase invoice. The dispatch of the electronic document is managed by an external provider of document exchange services. For more information, see [Data Exchange](../BusinessFunctionality/DataExchange/data-exchange.md).  
  
### To set up a document sending profile  
  
1.  In the **Search** box, enter **Document Sending Profiles**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)] --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify a code to identify the document sending profile in the system.|  
    |**Description**|Describe the document sending profile.|  
    |**Default**|Specify if the document sending profile will be used as the default profile for all customers.<br /><br /> The **Default** check box can only be selected for one Document Sending Profile record. To deselect a check box, select another check box.|  
    |**Printer**|Specify if the document is printed when you choose the **Post and Send** button. You can choose between the following options:<br /><br /> -   **No**: The document is not printed.<br />-   **Yes \(Use Default Settings\)**: The document is printed according to the default printer setup.<br />-   **Yes \(Prompt for Settings\)**: The document is printed according to settings that you make on the printer setup dialog.|  
    |**E\-Mail**|Specify if the document is sent by e\-mail to the customer when you choose the **Post and Send** button. You can choose between the following options:<br /><br /> -   **No**: An e\-mail is not created.<br />-   **Yes \(Use Default Settings\)**: The document is attached to an e\-mail to the customer according to the default settings for e\-mail sending. For more information, see [How to: Send Email Messages](../WorkingWithDynamics/how-to-send-email-messages.md).<br />-   **Yes \(Prompt for Settings\)**: The document is attached to an e\-mail according to settings that you make in the **Send Email** window.<br />     In the **E\-Mail Attachment** field, select the type of file to attach.|  
    |**Disk**|Specify if the document is saved to a file location when you choose the **Post and Send** button. You can choose between the following options:<br /><br /> -   **No**: No file is saved.<br />-   **PDF**: The document is saved as PDF to the location that you specify.<br />-   **Electronic Document**: The document is saved as an electronic documernt to the location that you specify.<br />     In the **Format** field, select the format of the electronic document.|  
    |**Electronic Document**|Specify if the document is sent as an electronic document that the customer can import into their system when you choose the **Post and Send** button. For more information, see [How to: Set Up Electronic Document Sending and Receiving](../BusinessFunctionality/DataExchange/how-to-set-up-electronic-document-sending-and-receiving.md).<br /><br /> You can choose between the following options:<br /><br /> -   **No**: An electronic document is not created.<br />-   **Through Document Exchange Service**: The document is sent as an elekctronic document.<br />     In the **Electronic Format** field, select the format of the electronic document.|  
    |**Electronic Format**|Specify which format to use for electronic document sending. For more information, see [Data Exchange](../BusinessFunctionality/DataExchange/data-exchange.md).|  
  
     The document sending profile is now ready to be selected in the **Document Sending Profile** field in the **Customer Card** window. See the next procedure.  
  
### To specify a sending profile on a customer card  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Open the card of the customer who you want to set up a sending profile for.  
  
     On the **Communication** FastTab, in the **Document Sending Profile** field, select a profile that you have set up as described in the previous procedure.  
  
### To set up electronic document formats  
  
1.  In the **Search** box, enter **Electronic Document Formats**, and then choose the related link.  
  
2.  In the **Electronic Document Format** window, create a new line for a new electronic document format that you want to set up.  
  
3.  Fill the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify a code to identify the electronic document format in the system.|  
    |**Description**|Describe the electronic document format.|  
    |**Usage**|Specify the type of document that the sending profile is used for, such as **Sales Invoice**.|  
    |**Codeunit ID**|Specify the codeunit that is used when you send electronic document in this document format.|  
  
     The electronic document format is now ready to be selected in the **Electronic Format** field in the **Document Sending Profile** window. For more information, see [How to: Set Up Electronic Document Sending and Receiving](../BusinessFunctionality/DataExchange/how-to-set-up-electronic-document-sending-and-receiving.md).  
  
## See Also  
 Document Sending Profile   
 Document Sending Profile   
 Electronic Format   
 Electronic Document Format   
 [How to: Set Up Electronic Document Sending and Receiving](../BusinessFunctionality/DataExchange/how-to-set-up-electronic-document-sending-and-receiving.md)   
 [Data Exchange](../BusinessFunctionality/DataExchange/data-exchange.md)   
 [How to: Send Email Messages](../WorkingWithDynamics/how-to-send-email-messages.md)   
 [How to: Invoice Sales](../Finance/how-to-invoice-sales.md)   
 [How to: Record Purchases](../Finance/how-to-record-purchases.md)