---
    title: EU Third-Party Purchase Transactions [SE]
    description: The following topic explains how to set up EU Third-Party Purchase Transactions with the Swedish version of Business Central.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/07/2023
    ms.author: bholtorf
---
# Set Up EU Third-Party Purchase Transactions in the Swedish Version
European Union (EU) third-party trade occurs when you receive a purchase invoice from a customer in one EU country/region and the products are sent to a different EU country/region without entering Sweden. The transaction amount must be identified and reported separately to comply with Swedish VAT reporting and VAT Information Exchange System (VIES) requirements. [!INCLUDE[prod_short](../../includes/prod_short.md)] includes Swedish enhancements that allow purchase transactions to be set up as EU third-party trade. Posted EU third-party transactions can then be filtered in VAT statements and excluded from the amount in the **Sales to Customer** column in the **VAT- VIES Declaration Tax Auth** report.  

> [!NOTE]
> **EU Third-Party Purchase Transactions** is a part of the Swedish localization. However, starting in version 22.1, Swedish localization is based on the W1 base app. The **EU Third-Party Purchase Transactions** functionality is moved to the global W1 extension installed by default. There are some minor functional changes. To learn more, see [EU third-party purchase transactions global feature](../../finance-how-to-eu3party-trade-purchase.md). The new feature can be used after you enable it in Feature Management. The old feature is automatically replaced with version 25.0.  

## To set up EU third-party purchase transactions  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2.  Select an existing purchase invoice, or choose the **New** action to create a new one.  
3.  On the **Invoice Details** FastTab, select the **EU 3-Party Trade** check box.  
4.  Choose the **OK** button.  

## See Also  
 [Report VAT to Tax Authorities](../../finance-how-report-vat.md)   
 [Sweden Local Functionality](sweden-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
