---
    title: OIOUBL Extension for Electronic Invoicing | Microsoft Docs
    description: This extension makes it easy to send electronically send sales and service invoices, credit memos, finance charge memos, and reminders to customers in the Danish public sector in an Offentlig Information Online UBL (OIOUBL) format.
    services: project-madeira
    documentationcenter: ''
    author: bholtorf

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 01/04/2018
    ms.author: bholtorf

---
# The OIOUBL Extension for Electronic Invoicing in Denmark
When you sell goods or services to customers in the Danish public sector, you must submit documents to the customer electronically in an Offentlig Information Online - Universal Business Language (OIOUBL) format.  

The OIOUBL extension in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] makes it easy to generate XML documents in an OIOUBL format for posted sales and service invoices, credit memos, and issued reminders (which include finance charge memos).  

The current requirements for sending electronic invoices are based on UBL version 2.0 standard. For more information, see the [OASIS UBL](http://go.microsoft.com/fwlink/?LinkId=212593) website. 

For more information about OIOUBL electronic invoicing, see the website for [Online OIOUBL Documentation](http://www.oioubl.info), and the [Frequently Asked Questions](https://www.digst.dk/It-loesninger/NemHandel/Spoergsmaal-og-svar.aspx) page on the Digitaliseringsstyrelsen website.  

## Getting Started with the OIOUBL Extension  
By default, the OIOUBL extension is installed in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. However, there are a few things to do before you can use the extension:

* Set up customers for OIOUBL by specifying an account code, the OILUBL profile to use to exchange documents, and the customer's Geographic Location Number (GLN).
* If you are using the Windows client, specify the file locations for the XML documents you generate. If you are using a browser version, such as the Web client, by default the files save to your Downloads folder.
* Optional: Set up payment methods, payment terms, and item charges.

For more information, see [How to: Set Up the OIOUBL Extension](how-to-set-up-oioubl.md).  

## See Also  
[Denmark Local Functionality](denmark-local-functionality.md)  
[How to: Set Up the OIOUBL Extension](how-to-set-up-oioubl.md)  
[How to: Create Electronic Documents in an OIOUBL Format](how-to-create-electronic-documents-by-using-oioubl.md)  
