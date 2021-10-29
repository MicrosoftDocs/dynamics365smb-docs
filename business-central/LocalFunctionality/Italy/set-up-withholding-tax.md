---
    title: Set Up Withholding Tax (IT)
    description: In the Italian version, companies must pay withholding tax to the government for third-party services and vendor purchases. Learn how to set this up.
    author: edupont04

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.search.keywords:
    ms.date: 10/29/2021
    ms.author: edupont

---
# Set Up Withholding Tax in the Italian Version

Companies must pay withholding tax to the government for third-party services and vendor purchases. Withholding tax is calculated during invoice payment rather than during invoice posting.

## To set up withholding tax codes

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Withhold Tax**, and then choose the related link for the **Setup** area for payables.  

2. Under **Lists**, choose **Code**.  

3. To open a new withholding code, on the **Home** tab, choose **New**.  

4. Enter information into the relevant fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

5. To add lines to the withhold code, on the **Navigate** tab, choose **Withhold Code Lines**.

6. Enter information into the relevant fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

7. Choose the **OK** button.

## To set up withholding tax for vendors

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.

2. Open the relevant vendor's vendor card.

3. Fill in the relevant fields. Specifically for withholding tax purposes, you must add the following information:

    * The vendor's personal data.
    * The contact details for the vendor.
    * The invoicing details for the vendor.
    * The payment information for the vendor.
    * The subcontracting information for the vendor.
    * The foreign trade information for the vendor.
    * The free lance fee - select the relevant withholding tax code in the **Withholding Tax Code** field to include the withholding tax information.

## To calculate withholding tax for purchase invoices

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.

2. Open the relevant purchase invoice.

3. Choose the **Withhold Taxes-Soc. Sec.** action.

4. In the **Withh. Taxes-Contribution Card** page, on the **Withhold Taxes** FastTab, in the **Withholding Tax Code** field, select the code for the withholding tax.

5. To calculate the withholding tax amount before posting, choose the **Calculate** action.  

## To make a vendor payment

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.

2. To create a new payment journal line, enter the relevant information in the fields.

3. To make a vendor payment, choose the **Post** action.  

    > [!NOTE]
    > The amount in the new line in the **Payment Journal** page is the withholding tax payment amount.

## See Also

[Print Withholding Tax Reports](how-to-print-withholding-tax-reports.md)  
[Set Up VAT](../../finance-setup-vat.md)  
[Record VAT](../../finance-how-report-vat.md)  
[Italy Local Functionality](italy-local-functionality.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]