---
    title: How to Set Up EU Third-Party Purchase Transactions
    description: European Union (EU) third-party trade occurs when you receive a purchase invoice from a customer in one EU country/region and the products are sent to a different EU country/region without entering Sweden.

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
# Set Up EU Third-Party Purchase Transactions
European Union (EU) third-party trade occurs when you receive a purchase invoice from a customer in one EU country/region and the products are sent to a different EU country/region without entering Sweden. The transaction amount must be identified and reported separately to comply with Swedish VAT reporting and VAT Information Exchange System (VIES) requirements. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes Swedish enhancements that allow purchase transactions to be set up as EU third-party trade. Posted EU third-party transactions can then be filtered in VAT statements and excluded from the amount in the **Sales to Customer** column in the **VAT- VIES Declaration Tax Auth** report.  

## To set up EU third-party purchase transactions  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Invoices**, and then choose the related link.  
2.  Select an existing purchase invoice, or choose the **New** action to create a new one.  
3.  On the **Invoice Details** FastTab, select the **EU 3-Party Trade** check box.  
4.  Choose the **OK** button.  

## See Also  
 [Report VAT to Tax Authorities](../../finance-how-report-vat.md)   
 [Sweden Local Functionality](sweden-local-functionality.md)
