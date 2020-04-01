---
    title: Withholding Tax
    description: Describes how withholding tax (WHT) works in New Zealand.
    services: project-madeira 
    documentationcenter: ''
    author: bholtorf
    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Withholding Tax
Withholding Tax (WHT) is tax withheld by a company when making a payment to a vendor, in which the full amount owed to that vendor is reduced by the tax withheld. The withheld tax is then remitted to tax authorities during the next Business Activity Statement (BAS) submission.  

The New Zealand government requires taxes to be withheld from payment to vendors under the following circumstances:  

* The vendor is a local supplier who has not supplied an New Zealand Inland Revenue Department number (IRD) before the payment is processed, and the individual transaction amount is greater than the specified threshold amount.  
* The vendor is a non-resident supplier and the payment is to be made to this non-resident entity in the form of interest, royalty, or dividend payments. Currently, there is no minimum threshold amount. Withholding rates may vary due to payment, or international tax treaties existing between New Zealand and the vendor's country.  

Fields within **WHT Business Posting Groups** and **WHT Product Posting Groups** must be set up on the **WHT Posting Setup** page so that the correct WHT calculations are made for each vendor.  

* **WHT Calculation Rule** – This field controls how calculation applies to the **WHT Minimum Invoice Amount**, or the invoice threshold amount. The following options exist:  

    - **Less than**  
    - **Less than or equal to**  
    - **Equal to**  
    - **Greater than**  
    - **Greater than or equal to**  

In New Zealand, WHT is not calculated if the individual invoice amount is less than or equal to the threshold amount. Companies should select **Less than or equal to**.  

* **WHT Minimum Invoice Amount** – Enter the invoice threshold amount.  
* **WHT %** – Enter the relevant WHT rate for the particular combination of **WHT Business Posting Group** and **WHT Product Posting Group**. If you do not wish to calculate any withholding amount, enter 0.00.  
* **Realised WHT Type** – Select **Payment** to calculate only the withholding amount at the time of payment. The other options of **Invoice** and **Earliest** do not apply to New Zealand.  
* **Payable WHT Account Code** – Enter the number of the G/L account to which you want to post **Purchase WHT** for the particular combination of **WHT Business Posting Group** and **WHT Product Posting Group**.  
* **Purch. WHT Adjustment Account No.** – Select an account number for **Purchase CR/Adj Note** adjustments.  
* **Revenue Types** – Drill down to the **WHT Revenue Types** page. These values determine how the combination of **WHT Business Posting Group** and **WHT Product Posting Group** are displayed in reports. You must enter a value in order for this combination to appear in the WHT reports.  

## WHT for Suppliers Without an IRD  
Ensure that there is a valid combination of **General Business** and **General Product Posting Groups** with the correct threshold. For example, in New Zealand today the minimum threshold is $75 with a rate of 46.50%.  

The percentage withheld is specified in **WHT Posting Setup**. The amount to be withheld is calculated automatically at the time of payment. The WHT certificate is printed automatically, and then sent to the vendor with payment. The WHT certificate explains the reasons for not sending the full invoiced amount.  

## WHT for Foreign Suppliers  
Ensure that a valid combination of **General Business** and **General Product Posting Groups** has been established for vendors for whom you need to withhold tax,other than for non-IRD.  

## See Also  
[Set Up Withholding Tax](how-to-set-up-withholding-tax.md)   
[Set Up Vendors Without IRD for Calculating the Withholding Tax](how-to-set-up-vendors-without-abn-for-calculating-the-withholding-tax.md)   
[Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)   
[Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)   
[View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)   
[New Zealand Local Functionality](new-zealand-local-functionality.md)
