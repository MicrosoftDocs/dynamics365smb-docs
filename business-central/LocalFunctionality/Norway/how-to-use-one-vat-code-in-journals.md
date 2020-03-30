---
    title: How to Use One VAT Code in Journals
    description: In Norway, you can use the feature one VAT code in a journal, so that you can post VAT by using a single field, VAT Code.

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
# Use One VAT Code in Journals
In Norway, you can use the feature one VAT code in a journal, so that you can post VAT by using a single field, **VAT Code**. After it is set up, the one VAT code is a quick way to fill in the commonly used VAT fields.  

To set up the VAT code for purchase orders and sales orders, the corresponding VAT business posting groups and the VAT product posting groups have to be defined.  

The VAT rate is calculated from the combination of VAT business posting groups, buyer information, and VAT product posting groups.  

## To create a VAT code  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Codes**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Enter information in the **Code**, **General Posting Type**, and **Description** fields for each VAT code.  
4.  Choose the **OK** button to close the **VAT Codes** page.  

 he following procedure explains the VAT posting setup.  

## To set up VAT posting  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Posting Setup**, and then choose the related link.  
2.  Choose the **New** action.  
3.  In the **VAT Posting Setup** card, fill in the following fields:  

    - **VAT Business Posting Group**  
    - **VAT Product Posting Group**  
    - **VAT Identifier**  
    - **VAT Percentage**  
    - **Sales VAT Account**  
    - **Purchase VAT Account**  

4.  In the **VAT Code** field, select a code from the list.  

Now, when you post a document in the general journal and close it, the information specified in the **VAT Posting Setup** card is applied.  

For example, the VAT rate posted in the journal is defined by the setup that you have specified on the **VAT Posting Setup** page.  

> [!NOTE]  
>  The **VAT Code** and the **Bal. VAT Code**  fields have been added to the journal. The **Bal. VAT Code** is the VAT code that is used to calculate the balancing account.  
>   
>  No changes are made to the posting.  

## See Also  
 [Norwegian VAT Codes](norwegian-vat-codes.md)
