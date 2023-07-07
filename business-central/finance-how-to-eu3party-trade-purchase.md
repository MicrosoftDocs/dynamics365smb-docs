---
    title: EU Third-Party Purchase Transactions
    description: The following topic explains how to set up and use EU Third-Party Purchase Transactions.

    author: altotovi    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 50, 51, 52, 187, 317
    ms.search.keywords: EU3P, EU 3-P, EU 3-Party
    ms.date: 07/07/2023
    ms.author: altotovi

---

# EU 3-Party Purchase functionality 

European Union (EU) third-party trade occurs when you receive a purchase invoice from a customer in one EU country/region and the products are sent to a different EU country/region without entering the country of residence. The transaction amount can be identified and reported separately to comply with some EU countries VAT reporting and VAT Information Exchange System (VIES) requirements. Business Central includes these enhancements that allow purchase transactions to be set up as EU third-party trade. Posted EU third-party transactions can then be filtered in VAT statements and excluded from the amount in the **Sales to Customer** column in the **VAT-VIES Declaration Tax Auth** report. 

Even if the feature is preinstalled as an extension, it isn't activated by default. Follow these steps to activate the feature.  

1.	Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, go to the **Feature Management** workspace, and then select the related link. 
2.	Find the **Feature update: Replace the existing EU 3-Party Purchase functionality with the new EU 3-Party Trade Purchase extension**. Then, in the **Enabled for** column, select **All users**.  

## To enable EU 3-Party Trade functionality in purchase  

1.	Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Setup**, and then select the related link. 
2.	In the **VAT Setup** page, mark the **Enable EU 3-Party Purchase** field. 

## To use EU 3-Party Trade functionality   

1.	Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoice** (or other purchase document), and then choose the related link. 
2.	Select an existing purchase invoice or choose the **New** action to create a new one. 
3.	On the **Invoice Details** FastTab, select the **EU 3-Party Trade** check box.   
4.	Choose the **OK** button.  

## To include or exclude EU 3-Party Trade records in the VAT Statement  

1.	Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement**, and then select the related link.  
2.	In the **VAT Statement** page, you can choose one of the following options for showing EU 3-Party Trade records using the **EU 3-Party Trade Filter** field.   

    | Option | Description | 
    |--------|-------------------------| 
    | All | This option will show all records regardless of using the **EU 3-Party Trade** field in documents. |  
    | EU3 | This option will show only records where the **EU 3-Party Trade** field in documents was marked. |   
    | Non-EU3 | This option will show only records where the **EU 3-Party Trade** field in documents was not marked. | 


## See also
[Financial Management](finance.md)  
[Work with Business Central](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
