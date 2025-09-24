---
author: brentholtorf
ms.topic: include
ms.date: 02/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

You can use the **General Ledger Setup** page to set up unrealized sales tax. You can also set up maximum correction tax amounts so that you can limit the tax correction amounts that are entered for sales and purchases. This allows you to overwrite the calculated tax. It's useful when there are rounding differences between what is calculated on the purchase order, and what is calculated on the purchase invoice from the vendor.

> [!NOTE]
> If you work with excise tax, the system doesn't allow you to change the **Tax Amount** field on the **Statistics** page for an invoice, for example to adjust for rounding. Therefore, if you set up an excise tax with more than two decimals and you experience a rounding difference compared to your vendor's invoices, then you must handle the rounding difference by posting an extra G/L entry. This way, the total matches the document amount. This posting could be made to an expense account dedicated to amount rounding.

## Set up unrealized sales tax  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. On the **General Ledger Setup** page > **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Pmt. Disc. Excl. Tax**|Select to calculate the payment discount on amounts excluding sales tax.|  
    |**Adjust for Payment Disc.**|Select to recalculate the tax amounts when you post payments that trigger payment discounts.<br/><br/> This field is used in the context of VAT, not sales tax.|
    |**Unrealized VAT**|Select if any of your sales tax jurisdictions allow you to pay your sales tax after you have been paid. If you don't select this check box, this function will be blocked for all sales tax jurisdictions.| 
1. Choose the **OK** button.  

## Set up unrealized tax for jurisdictions
  
1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Jurisdictions**, and then choose the related link.  
1. On the **Tax Jurisdictions** page, choose the **Edit List** action.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Unrealized Tax Type**|\<Blank\> – The unrealized tax feature isn't used for this tax jurisdiction.<br/><br/> or<br/><br/> **Percentage** – Each payment covers both tax amounts and invoice amounts in proportion to the remaining invoice amount. The paid tax amount is transferred from the unrealized tax account to the tax account.<br /><br/> or <br/><br/> **First** – Payments cover the tax first, and then the invoice amount.<br/><br/> or<br/><br/> **Last** – Payments cover the invoice amount first, and then the tax amount. In this case, nothing is transferred from the unrealized tax account to the tax account until the total invoice amount—exclusive of tax—has been paid.<br/><br/> or<br/><br/> **First (Fully Paid)** – Payments cover the tax first, but nothing is transferred to the tax account until the full tax amount has been paid.<br/><br/> or<br/><br/> **Last (Fully Paid)** – Payments cover the invoice amount first, but nothing is transferred to the tax account until the full tax amount has been paid. **Important:** This field is available on the **Tax Jurisdiction** page, but it isn't shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Unreal. Tax Acc (Sales)**|The general ledger account that you want to use to post calculated unrealized tax on sales transactions. **Important:**  This field is available on the **Tax Jurisdiction** page, but it isn't shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Unreal. Tax Acc (Purchases)**|The general ledger account that you want to use to post calculated unrealized tax on purchase transactions. <br></br>**Important:**  This field is available on the **Tax Jurisdiction** page, but it isn't shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Unreal. Rev. Charge (Purch.)**|The general ledger account that you want to use for posting calculated unrealized reverse-charge tax on purchase transactions. <br></br> **Important:**  This field is available on the **Tax Jurisdiction** page, but it isn't shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
1. Choose the **OK** button.  

## Set up adjustments for payment discounts in a tax posting group

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Posting Setup**, and then choose the related link.  
1. Choose the **Edit** action.  
1. On the **Tax Posting Setup Card** page, select the **Adjust for Payment Discount** check box.  

    > [!IMPORTANT]  
    > This field is available on the **VAT Posting Setup** page, but it isn't shown by default.
1. Choose the **OK** button.  

## Set up maximum tax correction amounts

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
1. On the **Sales Receivables Setup** page > **General** FastTab, select the **Allow Tax Difference** check box.  
1. Choose the **OK** button.  
1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
1. On the **Purchases & Payables Setup** page > **General** FastTab, select the **Allow Tax Difference** check box.  
1. Choose the **OK** button.  
1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. On the **General Ledger Setup** page, in the **Max. Tax Difference Allowed** field, enter the maximum tax correction amount that is allowed for the local currency.  

    > [!NOTE]  
    > In this field, if you enter USD 5, you may correct tax amounts by up to five dollars. To use the tax difference function, an amount must be entered in the **Max. Tax Difference Allowed** field.  
1. Choose the **OK** button.
