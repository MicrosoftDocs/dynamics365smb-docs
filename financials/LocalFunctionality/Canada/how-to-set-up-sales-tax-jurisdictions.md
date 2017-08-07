---
    title: How to: Set Up Sales Tax Jurisdictions | Microsoft Docs
    description: In the United States, states, counties, cities, and localities can charge sales tax.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up Sales Tax Jurisdictions
In the United States, states, counties, cities, and localities can charge sales tax.  
  
 In Canada, the federal government and provinces can charge sales tax. Companies collect and remit sales tax to these government authorities for products sold to end users.  
  
 Sales tax can also be charged to existing sales tax. For example, tax can be calculated on a sales invoice amount that already ../../includes the tax from other jurisdictions.  
  
 Tax amounts must be detailed in documents for each tax jurisdiction in Canada. Up to four jurisdictions can be displayed in a document, and jurisdictions that have the same print order are combined when they are printed.  
  
 Each tax area is a grouping of sales tax jurisdictions based on a particular geographic location. For example, the Miami, Florida, tax area ../../includes three sales tax jurisdictions: city (Miami), county (Dade), and state (Florida).  
  
### To set up sales tax jurisdictions  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Jurisdictions**, and then choose the related link.  
  
2.  In the **Tax Jurisdictions** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **New - Tax Jurisdictions** window, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code that you want to assign to the tax jurisdiction. You can enter up to 10 alphanumeric characters.|  
    |**Description**|A description of the tax jurisdiction.|  
    |**Tax Account (Sales)**|The general ledger account that you want to use to post calculated tax on sales transactions.|  
    |**Tax Account (Purchases)**|The general ledger account that you want to use to post calculated tax on purchase transactions.|  
    |**Reverse Charge (Purchases)**|The general ledger account that you want to use to post calculated reverse-charge tax on purchase transactions.|  
    |**Report-to Jurisdiction**|The tax jurisdiction that you want to associate with the jurisdiction that you are setting up.|  
    |**Country**|The country/region used for the sales tax calculation.|  
    |**Calculate Tax on Tax**|Select to calculate additional sales tax for the current jurisdiction. This tax is on top of the sales tax that has already been charged for previous jurisdictions. This is calculated based on the principle of tax on tax. **Important:**  This field is available in the **Tax Jurisdiction** window, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Print Description**|The description that prints on documents in place of the jurisdiction description. **Important:**  This field is available in the **Tax Jurisdiction** window, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Print Order**|The order in which the jurisdictions are printed. **Important:**  This field is available in the **Tax Jurisdiction** window, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
  
4.  Choose the **OK** button.  
  
### To set up sales tax areas  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Areas**, and then choose the related link.  
  
2.  In the **Tax Areas** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code that you want to assign to the tax area.|  
    |**Description**|The description for the tax area.|  
    |**Country**|The country/region used for the sales tax calculation.|  
    |**Round Tax**|The rounding amount used for the tax.|  
    |**Use External Tax Engine**|Select to indicate that an external sales tax engine is to be used when this tax area code is used.|  
  
4.  On the **Lines** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Tax Jurisdiction Code**|The tax jurisdiction code.|  
    |**Jurisdiction Description**|This field is populated when you enter the tax jurisdiction code.|  
    |**Calculation Order**|The order in which tax for each jurisdiction is calculated.|  
  
5.  Choose the **OK** button.  
  
## See Also  
 [How to: Set Up Sales Tax](how-to-set-up-sales-tax.md)   
 [How to: Set Up Sales Tax Groups](how-to-set-up-sales-tax-groups.md)   
 [How to: Set Up Sales Tax Details](how-to-set-up-sales-tax-details.md)   
 [How to: Set Up Unrealized Sales Tax and Sales Payment Discounts](how-to-set-up-unrealized-sales-tax-and-sales-payment-discounts.md)   
 [How to: Set Up Use Tax and Purchase Tax](how-to-set-up-use-tax-and-purchase-tax.md)