---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Set Up the Additional Reporting Currency
Follow these steps to set up the additional reporting currency:  
  
-   Specify general ledger accounts for posting exchange rate adjustments.  
  
-   Specify the exchange rate adjustment method for all general ledger accounts.  
  
-   Specify the exchange rate adjustment method for VAT entries.  
  
-   Activate the additional reporting currency.  
  
### To specify general ledger accounts for posting exchange rate adjustments  
  
1.  In the **Search** box, enter **Currencies**, and then choose the related link.  
  
2.  In the **Currencies** window, specify the following fields for the additional reporting currency.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] --> --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Realized G\/L Gains Account**|The general ledger account to which exchange rate gains for currency adjustments between LCY and the additional reporting currency will be posted.|  
    |**Realized G\/L Losses Account**|The general ledger account to which exchange rate losses for currency adjustments between LCY and the additional reporting currency will be posted.|  
    |**Residual Gains Account**|The general ledger account to which residual amounts that are gains are posted if you post in the general ledger application area in both LCY and an additional reporting currency.|  
    |**Residual Losses Account**|The general ledger account to which residual amounts that are losses are posted if you post in the general ledger application area in both LCY and an additional reporting currency.|  
  
> [!NOTE]  
>  Residual amounts can occur when FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> rounds debit and credit amounts that have been converted from LCY to an additional reporting currency.  
  
 For each general ledger account, you must specify how general ledger amounts for that account will be adjusted for exchange rate fluctuations between LCY and the additional reporting currency.  
  
### To specify the exchange rate adjustment method for all general ledger accounts  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  In the **Chart of Accounts** window, select the relevant account.  
  
3.  On the **Home** tab, in the **Manage** group, choose **Edit** to open the **G\/L Account Card** window.  
  
4.  On the **Reporting** FastTab, select the correct method in the **Exchange Rate Adjustment** field.  
  
     If you post in an additional reporting currency, specify in the **Exchange Rate Adjustment** field how this general ledger account will be adjusted for exchange rate fluctuations between LCY and the additional reporting currency.  
  
     The following table shows the options to choose from.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)] --> -->|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |----------------------------------|---------------------------------------|  
    |**No Adjustment**|No exchange rate adjustment is made to the general ledger account. This is the default option.<br /><br /> **NOTE:** This option should be selected if the exchange rate between the LCY and additional reporting currency is always fixed.|  
    |**Adjust Amount**|The LCY amount is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G\/L Gains Account** and **Realized G\/L Losses Account** fields in the **Currencies** window.|  
    |**Adjust Additional-Currency Amount**|The additional reporting currency is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G\/L Gains Account** and **Realized G\/L Losses Account** fields in the **Currencies** window.|  
  
     Exchange rate gains and losses are posted first when you run the **Adjust Exchange Rates** batch job. In that batch job, the adjustment exchange rate is identified in the **Currency Exchange Rates** window, and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the general ledger entry are compared to determine whether there is an exchange rate gain or loss. The batch job uses the option that you select in the **Exchange Rate Adjustment** field to determine whether to calculate and post exchange rate gains or losses for general ledger accounts.  
  
5.  Close the **G\/L Account Card** window.  
  
### To specify exchange rate adjustment method for VAT entries  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  In the **General Ledger Setup** window, on the **Reporting** FastTab, select the required method in the **VAT Exchange Rate Adjustment** field.  
  
3.  If you post in an additional reporting currency, you can specify in the **VAT Exchange Rate Adjustment** field how the accounts set up for VAT posting in the **VAT Posting Setup** window will be adjusted for exchange rate fluctuations between LCY and the additional reporting currency.  
  
     When you run the **Adjust Exchange Rates** batch job, the adjustment exchange rate is identified in the **Currency Exchange Rate** window and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the VAT entry are compared to determine whether there is an exchange rate gain or loss. The batch job uses the option that you select in this field to determine how to post exchange rate gains or losses for VAT accounts.  
  
     You have the same options as with general ledger entries but in this case the entries adjusted will be the VAT entries.  
  
    |[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |----------------------------------|---------------------------------------|  
    |**No Adjustment**|No exchange rate adjustment is made to the general ledger account. This is the default option.|  
    |**Adjust Amount**|The LCY amount is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G\/L Gains Account** and **Realized G\/L Losses Account** fields in the **Currencies** window.|  
    |**Adjust Additional-Currency Amount**|The additional reporting currency is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G\/L Gains Account** and **Realized G\/L Losses Account** fields in the **Currencies** window.|  
  
### To activate the additional reporting currency  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  In the **General Ledger Setup** window, on the **Reporting** FastTab, choose the **Additional Reporting Currency** field to select the additional currency that you want to report in.  
  
3.  When you leave the field, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] displays a confirmation message describing the effects of activating the additional reporting currency.  
  
4.  Choose the **Yes** button to confirm that you want to activate the currency.  
  
5.  The **Adjust Add. Reporting Currency** batch job opens. This batch job converts LCY amounts on existing entries to the additional reporting currency. The batch job uses a default exchange rate copied from the exchange rate that is valid on the work date in the **Currency Exchange Rates** window. Residual amounts that occur on conversion of LCY to additional reporting currency are posted to the residual gains and losses accounts specified in the **Currencies** window. The posting date and document number for these entries is the same as the original general ledger entry. After all these residual entries are posted, the batch job then posts a rounding entry on the closing date of each closed year to the retained earnings account. This is to make sure that the ending balance of the income accounts for each closed years is 0 in both LCY and the additional reporting currency.  
  
6.  Choose the **OK** button to run the batch job.  
  
7.  After running this batch job, amounts on the following existing entries will be in both LCY and in the additional reporting currency:  
  
    -   General Ledger Entries  
  
    -   Item application entries  
  
    -   VAT entries  
  
    -   Job ledger entries  
  
    -   Value entries  
  
    -   Production order lines  
  
    -   Prod. order ledger entries  
  
     In addition, all future entries of the same type will have amounts recorded in both LCY and the additional reporting currency.  
  
> [!NOTE]  
>  The **Add. Reporting Currency** field will only be activated after you choose the **OK** button in the **Adjust Add. Reporting Currency** batch job.  
  
## See Also  
 [About Using Additional Reporting Currencies](../Finance/about-using-additional-reporting-currencies.md)   
 Realized G\/L Gains Account   
 Realized G\/L Losses Account   
 Residual Gains Account   
 Residual Losses Account