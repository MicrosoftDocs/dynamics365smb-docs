---
    title: How to Set Up Unrealized Sales Tax and Sales Payment Discounts | Microsoft Docs
    description: You can use the General Ledger Setup page to set up unrealized sales tax. You can also set up maximum correction tax amounts so that you can limit the tax correction amounts that are entered for sales and purchases. This allows you to overwrite the calculated tax when there are rounding differences between what is calculated on the purchase order, and what is calculated on the purchase invoice from the vendor.
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
# Set Up Unrealized Sales Tax and Sales Payment Discounts
You can use the **General Ledger Setup** page to set up unrealized sales tax. You can also set up maximum correction tax amounts so that you can limit the tax correction amounts that are entered for sales and purchases. This allows you to overwrite the calculated tax when there are rounding differences between what is calculated on the purchase order, and what is calculated on the purchase invoice from the vendor.  

## To set up unrealized sales tax  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.  
2.  On the **General Ledger Setup** page, on the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Pmt. Disc. Excl. Tax**|Select to calculate the payment discount on amounts excluding sales tax.|  
    |**Adjust for Payment Disc.**|Select to recalculate the tax amounts when you post payments that trigger payment discounts.<br /><br /> This field is used in the context of VAT, not sales tax.|  
    |**Unrealized VAT**|Select if any of your sales tax jurisdictions allow you to pay your sales tax after you have been paid. If you do not select this check box this function will be blocked for all sales tax jurisdictions.|  
3.  Choose the **OK** button.  

## To set up unrealized tax for jurisdictions  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Jurisdictions**, and then choose the related link.  
2.  On the **Tax Jurisdictions** page, choose the **Edit List** action.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Unrealized Tax Type**|<Blank> – The unrealized tax feature is not used for this tax jurisdiction.<br /><br /> –or–<br /><br /> **Percentage** – Each payment covers both tax amounts and invoice amounts in proportion to the remaining invoice amount. The paid tax amount is transferred from the unrealized tax account to the tax account.<br /><br /> –or–<br /><br /> **First** – Payments cover the tax first, and then the invoice amount.<br /><br /> –or–<br /><br /> **Last** – Payments cover the invoice amount first, and then the tax amount. In this case, nothing will be transferred from the unrealized tax account to the tax account until the total invoice amount—exclusive of tax—has been paid.<br /><br /> –or–<br /><br /> **First (Fully Paid)** – Payments cover the tax first, but nothing is transferred to the tax account until the full tax amount has been paid.<br /><br /> –or–<br /><br /> **Last (Fully Paid)** – Payments cover the invoice amount first, but nothing is transferred to the tax account until the full tax amount has been paid. **Important:**  This field is available on the **Tax Jurisdiction** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Unreal. Tax Acc (Sales)**|The general ledger account that you want to use to post calculated unrealized tax on sales transactions. **Important:**  This field is available on the **Tax Jurisdiction** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Unreal. Tax Acc (Purchases)**|The general ledger account that you want to use to post calculated unrealized tax on purchase transactions. **Important:**  This field is available on the **Tax Jurisdiction** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Unreal. Rev. Charge (Purch.)**|The general ledger account that you want to use for posting calculated unrealized reverse-charge tax on purchase transactions. **Important:**  This field is available on the **Tax Jurisdiction** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
4.  Choose the **OK** button.  

## To set up adjustments for payment discounts in a tax posting group  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Posting Setup**, and then choose the related link.  
2.  Choose the **Edit** action.  
3.  On the **Tax Posting Setup Card** page, select the **Adjust for Payment Discount** check box.  

    > [!IMPORTANT]  
    >  This field is available on the **VAT Posting Setup** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]  
4.  Choose the **OK** button.  

## To set up maximum tax correction amounts  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
2.  On the **Sales Receivables Setup** page, on the **General** FastTab, select the **Allow Tax Difference** check box.  
3.  Choose the **OK** button.  
4.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
5.  On the **Purchases & Payables Setup** page, on the **General** FastTab, select the **Allow Tax Difference** check box.  
6.  Choose the **OK** button.  
7.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.  
8.  On the **General Ledger Setup** page, in the **Max. Tax Difference Allowed** field, enter the maximum tax correction amount that is allowed for the local currency.  

    > [!NOTE]  
    >  In this field, if you enter USD 5, you may correct tax amounts by up to five dollars. To use the tax difference function, an amount must be entered in the **Max. Tax Difference Allowed** field.  
9. Choose the **OK** button.  

## See Also  
[United States Local Functionality](united-states-local-functionality.md)  
[Reporting Sales Tax in the US](us-sales-tax.md)  
[Finance](../../finance.md)  
[Setting Up Finance](../../finance.md)
