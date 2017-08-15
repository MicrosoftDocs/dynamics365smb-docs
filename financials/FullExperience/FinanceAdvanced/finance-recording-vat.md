---
    title: Recording VAT on Sales and Purchase Documents | Microsoft Docs
    description: In EU countries/regions, every sales and purchase transaction is subject to VAT calculations.
    services: project-madeira
    documentationcenter: ''
    author: bholtorf

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/15/2017
    ms.author: bholtorf

---
# Recording VAT for Sales and Purchases
In EU countries/regions, every sales and purchase transaction is subject to VAT calculations.  
  
## Calculating and Displaying VAT Amounts in Sales and Purchase Documents  
 You can calculate and display VAT amounts in sales and purchase documents differently depending on the type of customer or vendor that you are dealing with. You can also override the VAT amount calculated by the program to match the VAT amount calculated by your vendor on a given transaction.  
  
### Correcting reverting VAT amounts  
You can make corrections to posted VAT entries. This allows you to change the total sales or purchase VAT amounts without changing the VAT base. The feature may be used, for example, if you receive an invoice from a vendor who has calculated VAT incorrectly.  

If a payment discount has been calculated on the basis of an invoice amount that includes VAT, you have the possibility of having the payment discount part of the VAT amount reverted when the payment discount is granted. Note that you must activate the **Adjust for Payments Disc.** field in both the general ledger setup in general and the VAT posting setup for specific combinations of a VAT business posting group and a VAT product posting group.  
  
### Unit Price and Line Amount Including/Excluding VAT  
When you choose an item in the **No.** field in a sales document, the program also fills in the **Unit Price** field. The unit price is calculated and transferred from either the **Item** card or from the item prices allowed for the item and customer. The program only calculates the **Line Amount** when you enter a quantity for the line.  
  
In cases where you are selling to retail consumers, you may want your sales document prices to be displayed including VAT both on screen and when printed. To do this, you can select the **Prices Including VAT** check box in the document header.  
  
### Checked and unchecked fields  
If the **Prices Including VAT** field is selected, the **Unit Price** and **Line Amount** field will be updated to include VAT and the field names will also reflect this.  
  
If the field is not selected, the program will fill in the **Unit Price** and **Line Amount** field excluding VAT and the field names will reflect this.  
  
### Prices Including VAT Defaults on Customer and Item Cards  
You can set up the default setting of the **Prices Including VAT** for all sales documents for a customer in the **Prices Including VAT** field on the **Customer** card.  
  
You can also set up item prices to include or exclude VAT. Normally, item prices contained in the Item Card will be the price excluding VAT. The program uses the information from the **Price Includes VAT** field on the **Item** card to determine the unit price amount for sales documents.  
  
The following table provides an overview of how the program calculates the unit price amounts for a sales document when you have not set up prices in the **Sales Prices** window:  
  
|**Price Includes VAT field on Item Card**|**Prices Including VAT field in Sales Header**|**Action Performed**|  
|-----------------------------------------------|----------------------------------------------------|--------------------------|  
|No check mark|No check mark|The **Unit Price** on the Item Card is copied to **Unit Price Excl. VAT** field on the sales lines.|  
|No check mark|Check mark|The program calculates the VAT amount per unit and adds to the **Unit Price** on the Item Card. This total Unit Price is then entered in the **Unit Price Incl. VAT field** on the sales lines.|  
|Check mark|No check mark|The program calculates the VAT amount included in the **Unit Price** on the Item Card using the VAT% related to the VAT Bus. Posting Gr. (Price) and the VAT Prod. Posting Group combination. The **Unit Price** on the Item Card, reduced by the VAT amount, is then entered in the **Unit Price Excl. VAT** field in the sales lines.|  
|Check mark|Check mark|The **Unit Price** on the Item Card is copied to **Unit Price Incl. VAT** field on the sales lines.|  
  
## See Also  
[How to: Report VAT](finance-how-report-vat.md)   
[How to: Set Up VAT](finance-setup-vat.md)   