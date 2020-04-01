---
    title: Equivalence Charges (EC)
    description: An Equivalence Charge (EC) is a tax that is used in retail sales and in activities that do not follow VAT rules. Under EC rules, companies must pay a surcharge to their vendors when purchasing goods, in addition to the usual VAT.

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
# Equivalence Charges (EC)
An Equivalence Charge (EC) is a tax that is used in retail sales and in activities that do not follow VAT rules. Under EC rules, companies must pay a surcharge to their vendors when purchasing goods, in addition to the usual VAT. However, when selling goods, only VAT can be charged. Some general posting groups must have an EC percentage in addition to the VAT percentage. This information is tracked separately, but in order to minimize changes, both taxes are usually combined.  

The **EC %** field is a separate field in the **Purchase Line**, **Sales Line**, **Sales Line Archive** and **Purchase Line Archive** tables. However, in sales and purchase lines, both taxes are combined and the value is displayed in the **VAT %** field. The **VAT + EC %** field is used when these values are combined. At the time of posting, the VAT percentage and the EC percentage are inserted in the **VAT Entry** table. This makes it possible to print the **Sales Invoice Book** report and the **Purchases Invoice Book** report.  

## See Also  
[Spain Local Functionality](spain-local-functionality.md)
