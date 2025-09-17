---
title: Setting up TDS by Customer as per the Income Tax Act, 1961 provisions
description: Describes the basic setups required according to the Income Tax Act, 1961.
author: v-debapd 
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS setup, state code, company information, location master, Customer Card, customer master, posting setup, concessional codes, TDS section, assessee code, T.A.N, accounting period, TDS rates, setup types
ms.date: 06/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up TDS by customer based on the Income Tax Act, 1961 provisions

Business Central has included Tax Deducted at Source (TDS) by Customer Feature to Indian Localization.

TDS is a withholding tax, where tax is deducted by the customer, at the time of making the payment or booking of the invoice, whichever is earlier. As per the Income Tax Act, 1961, tax needs to be deducted by the payer, when the payment is of a specific nature.
If the TDS is deducted by the customer (deductor), then the user (deductee) has to calculate TDS on the invoice or revenue and keep a track of TDS deducted. The deductor has to provide the deductee a TDS certificate.

## Set up TDS

### TDS has two types of setup

- Automatic - These setups are done through Tax Engine.
- Manual - These setups are done manually by the business users.

### Following is the list of setups, which are preconfigured with help of **Tax Engine**

- Tax Types
- Tax Entities
- Components
- Attributes
- Rate Setup

For more information about Automatic Setup, see **Tax Engine** Information.

### The following setups are required to be configured manually

- [TDS Rate](tds-for-customer-overview.md#set-up-tds-rates)
- [Tax Accounting Period](tds-for-customer-overview.md#set-up-tax-accounting-period)
- [T.A.N](tds-for-customer-overview.md#set-up-tan)
- [Assessee Code](tds-for-customer-overview.md#set-up-assessee-code)
- [TDS Section](tds-for-customer-overview.md#set-up-tds-section)
- [Concessional Code](tds-for-customer-overview.md#set-up-concessional-codes)
- [TDS Posting Setup](tds-for-customer-overview.md#set-up-tds-posting-setup)
- [TDS on Customer Master](tds-for-customer-overview.md#set-up-tds-on-customer-master)
- [TDS on Location Master](tds-for-customer-overview.md#set-up-tds-on-location-master)
- [TDS on Company Information](tds-for-customer-overview.md#set-up-tds-on-company-information)
- [TDS on State Code](tds-for-customer-overview.md#set-up-tds-on-state-code)

## Set up TDS rates

Rate of TDS is defined in combination of TDS section and assessee code.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Type** > **TDS** > **Action** > **Tax Rates**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Section Code**|Specifies the TDS section code.|
    |**Assessee Code**|Specifies the assessee code.|
    |**Effective Date**|Specifies the date from which rate is effective.|
    |**Concessional Code**|Specifies the concessional code.|
    |**Nature of Remittance**|Specifies whether the nature of remittance is applicable or not.|
    |**Act Applicable**|Specifies the applicable act.|
    |**Currency Code**|Specifies the currency code.|
    |**TDS %**|Specifies the TDS rate.|
    |**Non PAN TDS %**|Specifies the TDS rate in case of non availability of PAN.|
    |**Surcharge %**|Specifies the surcharge rate.|
    |**eCESS %**|Specifies the eCess rate.|
    |**SHE Cess %**|Specifies the SHE Cess rate.|
    |**Surcharge Threshold Amount**|Specifies the threshold amount applicable for surcharge.|
    |**TDS Threshold Amount**|Specifies the threshold amount applicable for TDS.|
    |**Per Contract Value**|Specifies the per contract value.|

## Set up tax accounting period

Tax Accounting period and quarters need to be defined for TDS calculation.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Acc. Period Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid tax type.|  
    |**Description**|Specify the description of the tax type.|

1. Select the **Tax Type** > **Action** > **Tax Accounting Period** > **Create Year**, fill the following information and accounting period is created.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Tax Type**|Select the valid tax type.|  
    |**Starting Date**|Specify the starting date of the accounting period.|
    |**No. of Periods**|Specify the number of periods.|
    |**Period Length**|Specify the length of the period.|

## Set up T.A.N

Tax Deduction Account Number (T.A.N) allotted to a legal entity can be more than one, depending on the number of branch locations from where the legal entity files its TDs returns. All the account numbers allotted to a legal entity need to be captured here.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **T.A.N Nos.**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid registration number provided by authority.|  
    |**Description**|Specify the description of the registration number.|

## Set up assessee code

Income Tax Act 1961 defines 'Assessee' as a person by whom any tax or any other sum of money is payable under this Act. The rates of TDS are different for different types of Assessee.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Assessee Codes**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid Assessee Code, for example, IND, COM.|  
    |**Description**|Enter the description of the assessee code.|
    |**Type**|Select the type of the assessee from drop-down list as Company or Others.|

## Set up TDS section

TDS Section represents the various sections under which tax deduction takes place as per the Income Tax Act 1961.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **TDS Sections**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid TDS Section applicable as per the Income Tax Act, 1961|  
    |**Description**|Enter the description of the mentioned TDS Section.|
    |**e-TDS**|Specifies the section code to be used in the tds return.|

## Set up concessional codes

Concessional codes are used for cases authorized for concessional rates exclusively defined by the government.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Concessional Codes**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid Concessional Codes applicable as per the Income Tax Act|  
    |**Description**|Enter the description of the mentioned Concessional Codes|

## Set up TDS posting setup

Specifies the general ledger account for each TDS Section defined in the system. System updates the TDS receivable amount in the defined general ledger account.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **TDS Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**TDS Section**|Specifies the relevant TDS section|  
    |**Effective Date**|Specifies the start date of the setup line|
    |**TDS Receivable Account**|Specifies the general ledger account in which receivable account is posted.|

## Set up TDS on customer master

TDS Section and concessional codes need to be defined for each customer, who is liable to deduct TDS. Multiple TDS sections can be configured for one customer.

- To define the TDS Sections on the Customer Card

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Customer** > **Customer** > **Customer Allowed Sections** and then choose the related link.
  1. **Assessee Code** needs to be filled on the customer master.
  1. **PAN** needs to be filled on customer master, PAN is mandatory for TDS calculation for customer.
  1. Fill in the fields as described in the following table.

      |Field|Description|  
      |---------------------------------|---------------------------------------|
      |**TDS Section**|Select the valid section from lookup list depending on the kind of services provided by the customer.|
      |**TDS Section Description**|Enter the description of the selected section.|
      |**TDS Certificate Receivable**|This field should be marked as true.|
      |**Threshold Overlook**|Place a check mark in this field to overlook the TDS Threshold amount defined in 'Tax Rates'|
      |**Surcharge Overlook**|Place a check mark in this field to overlook the Surcharge Threshold amount defined in 'Tax Rates'|

- To define the concessional code on customer card

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Customer** > **Customer** > **TDS Customer Concessional Codes** and then choose the related link.
  1. Fill in the fields as described in the following table.

      |Field|Description|  
      |---------------------------------|---------------------------------------|
      |**Section**|Select the valid section from lookup list depending on the kind of services provided by customer.|
      |**Concessional Code**|Select the valid concessional code from lookup list depending on the kind of services provided by customer.|
      |**Certificate No.**|Certificate number provided by the customer can be defined to justify the lower tax deduction.  |

## Set up TDS on location master

**T.A.N** needs to be defined in locations from where the company files its returns.

## Set up TDS on company information

- Following information need to be defined in company information.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**T.A.N. No.**|Specifies the TAN No. of the legal entity.|
    |**P.A.N No.**|Specifies the PAN of the legal entity.|
    |**Deductor Category**|Specifies the deductor category of the legal entity.|
    |**PAO Code**|Specifies the PAO code.|
    |**PAO Registration No.**|Specifies PAO registration number.|
    |**DDO Code**|Specifies DDO code.|
    |**DDO Registration No.**|Specifies the DDO registration number.|
    |**Ministry Type**|Specifies the Ministry type.|
    |**Ministry Code**|Specifies the Ministry code.|

## Set up TDS on state code

**State Code for eTDS/TCS** needs to be defined in States master.

## Related information

[TDS Calculation for Customer](TDS-Calculation-for-Customer.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
