---
    title: OIOUBL Extension for Electronic Invoicing | Microsoft Docs
    description: This extension makes it easy to send electronically send sales and service invoices, credit memos, finance charge memos, and reminders to customers in the Danish public sector in an Offentlig Information Online UBL (OIOUBL) format.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# The OIOUBL Extension for Electronic Invoicing in Denmark
When you sell goods or services to customers in the Danish public sector, you must submit documents to the customer electronically in an XML file that is structured to meet the requirements of one or more Offentlig Information Online - Universal Business Language (OIOUBL) profiles.  

The OIOUBL extension in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] makes it easy to generate these XML documents for posted sales and service invoices, credit memos, and issued reminders (which include finance charge memos).  

The current requirements for sending electronic invoices are based on UBL version 2.0 standard. For more information, see the [https://aka.ms/OasisUblSite](https://aka.ms/OasisUblSite) web site.

For more information about OIOUBL in general, see the website for [Online OIOUBL Documentation](http://www.oioubl.info/classes/da/index.html), and the [Digitaliseringsstyrelsen](https://digst.dk/) website.  

## Getting Started with the OIOUBL Extension  
By default, the OIOUBL extension is installed in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. However, there are a few things to do before you can use the extension:

* Set up payment methods, payment terms, and item charges.
* Set up customers for OIOUBL by specifying an account code, the OIOUBL profile to use to exchange documents, and the customer's Geographic Location Number (GLN).

For more information, see [Set Up the OIOUBL Extension](how-to-set-up-oioubl.md).  

## See Also

[Denmark Local Functionality](denmark-local-functionality.md)  
[Set Up the OIOUBL Extension](how-to-set-up-oioubl.md)  
[Create Electronic Documents in an OIOUBL Format](how-to-create-electronic-documents-by-using-oioubl.md)  
