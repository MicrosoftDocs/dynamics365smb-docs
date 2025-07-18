---
title: Setting up Tax Deducted at Source, as per the provisions of the Income Tax Act, 1961
description: Describes the basic setups that are required by the provisions of the Income Tax Act, 1961.
author: v-debapd  
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS setup, state code, company information, location master, Vendor Card, vendor master, rounding precision, posting setup, act applicable, remittances, concessional codes, TDS section, assessee code, T.A.N, accounting period, TDS rates, setup types
ms.date: 06/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up Tax Deducted at Source (TDS) as per the Income Tax Act, 1961 provisions

Business Central has included Tax Deducted at Source (TDS) Feature to Indian Localization.

**TDS** means **Tax Deducted at Source**. The concept of TDS was introduced with an aim to collect tax from the very source of income. As per this concept, a person (deductor) who is liable to make payment of specified nature to any other person (deductee) shall deduct tax at source and remit the same into the account of the Central Government

Income from several sources is subjected to TDS. Presently this concept of TDS is also used as an instrument in enlarging the tax base. Some of such incomes subjected to TDS are salary, interest, dividend, interest on securities, winnings from lottery, horse races, commission and brokerage, rent, fees for professional and technical services, and payments to nonresidents.

The Income Tax Act, 1961 specifies that tax deduction is to be made, for the specified incomes, on credit or on payment, whichever is earlier.

## Set up TDS

### TDS has two different types of setups

- Automatic - These setups are done through Tax Engine.
- Manual - These setups are done manually by the business users.

#### Following is the list of setups, which are preconfigured with help of **Tax Engine**

- Tax Types
- Tax Entities
- Components
- Attributes
- Rate Setup

For more information about Automatic Setup, see **Tax Engine** Information.

#### The following setups are required to be set up manually

- [TDS Rate](tds-overview.md#to-set-up-tds-rates)
- [Tax Accounting Period](tds-overview.md#to-set-up-tax-accounting-period)
- [T.A.N](tds-overview.md#to-set-up-tan)
- [Assessee Code](tds-overview.md#to-set-up-assessee-code)
- [TDS Section](tds-overview.md#to-set-up-tds-section)
- [Concessional Code](tds-overview.md#to-set-up-concessional-codes)
- [TDS Nature of Remittances](tds-overview.md#to-set-up-tds-nature-of-remittances)
- [Act Applicable](tds-overview.md#to-set-up-act-applicable)
- [TDS Posting Setup](tds-overview.md#to-set-up-tds-posting-setup)
- [TDS Rounding Precision](tds-overview.md#to-set-up-tds-rounding-precision)
- [TDS in Vendor Master](tds-overview.md#to-set-up-tds-in-vendor-master)
- [TDS in Location Master](tds-overview.md#to-set-up-tds-in-location-master)
- [TDS in Company Information](tds-overview.md#to-set-up-tds-in-company-information)
- [TDS in State Code](tds-overview.md#to-set-up-tds-in-state-code)

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

1. Select the Tax Type > Action > Tax Accounting Period > Create Year, fill the following information and accounting period is created.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Tax Type**|Select the valid tax type.|  
    |**Starting Date**|Specify the starting date of the accounting period.|
    |**No. of Periods**|Specify the number of periods.|
    |**Period Length**|Specify the length of the period.|

## Set up T.A.N

Tax Deduction Account Number (T.A.N) allotted to a company can be more than one, depending on the number of branch locations from where the company files its returns. All the account numbers allotted to a company need to capture here.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **T.A.N Nos.**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid registration number provided by authority.|  
    |**Description**|Specify the description of the registration number.|

> [!TIP]
> It's mandatory to enter the T.A.N, on all TDS Transactions.

## Set up assessee code

Income Tax Act 1961 defines 'Assessee' as a person by whom any tax or any other sum of money is payable under this Act. The rates of TDS are different for different types of Assessee.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Assessee Codes**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid Assessee Code, for example, IND, COM.|  
    |**Description**|Enter the description of the assessee code.|
    |**Type**|Select the type of the assessee from drop-down list as Company or Others.|

> [!TIP]
> Type should be selected correctly while creating Assessee codes as it reflects in eTDS returns.

## Set up TDS section

TDS Section represents the various sections under which tax deduction takes place as per the Income Tax Act 1961.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **TDS Sections**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid TDS Section applicable as per the Income Tax Act, 1961.|  
    |**Description**|Enter the description of the mentioned TDS Section.|
    |**e-TDS**|Specifies the section code to be used in the TDS return.|

> [!TIP]
> User can create any number of subsections for a section using **Add Sub Section** function.

## Set up concessional codes

Concessional codes are used for cases authorized for concessional rates exclusively defined by the government.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Concessional Codes**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid Concessional Codes applicable as per the Income Tax Act.|  
    |**Description**|Enter the description of the mentioned Concessional Codes.|

## Set up TDS nature of remittances

Specifies the type of remittance.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Nature of Remittances**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid nature of remittance code applicable.|
    |**Description**|Enter the description of the code.|

## Set up act applicable

Specifies the Act under which income from Nonresident Indians is taxed either the Income Tax Act (IT-Act), or as per the relevant rates prescribed in the relevant Double Tax Avoidance Agreement (DTAA).

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Act Applicable**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the valid Concessional Codes applicable as per the Income Tax Act, 1961.|

## Set up TDS posting setup

Specifies the general ledger account for each TDS Section defined in the system. System updates the TDS payable amount in the defined general ledger account.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **TDS Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**TDS Section**|Enter the valid TDS Section.|
    |**Effective Date**|Specifies the starting date.|
    |**TDS Account**|Specifies the general ledger account for posting of TDS payable amount.|

## Set up TDS rounding precision

Rounding precision for each and every component can be defined in system.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Type** > Select **TDS** > **Tax Component**, and then choose the related link.
1. Define the relevant rounding precision against each tax components.

## Set up TDS in vendor master

TDS Section and concessional codes need to be defined for each vendor that is liable to TDS. Multiple TDS sections can be attached to one vendor.

- To define the TDS Sections in the Vendor Card

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Vendors** > **Navigate** > **Allowed Sections** and then choose the related link.
  1. **Assessee Code** needs to be filled on the vendor master.
  1. **PAN** needs to be filled on vendor master, in case of no PAN is provided, higher rate of TDS is deducted.
  1. Fill in the fields as described in the following table.

      |Field|Description|  
      |---------------------------------|---------------------------------------|
      |**TDS Section**|Select the valid section from lookup depending on the kind of services provided by the vendor.|
      |**TDS Section Description**|Enter the description of the selected section.|
      |**Default Section**|Mark true if the section needs to be defined as default section.|
      |**Threshold Overlook**|Place a check mark in this field to overlook the TDS Threshold amount defined in 'Tax Rates'|
      |**Surcharge Overlook**|Place a check mark in this field to overlook the Surcharge Threshold amount defined in 'Tax Rates'|
      |**Non Resident Payment**|Identify if the TDS Section deals with nonresident. This identification helps the system to generate eTDS for Non-Residents.|
      |**Nature of Remittance**|Select the Nature of Remittance.|
      |**Act Applicable**|Select  applicable act for generating in eTDS returns.|

- To define the concessional code in vendor card

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Vendors** > **Navigate** > **TDS Concessional Codes**, and then choose the related link.
  1. Fill in the fields as described in the following table.

      |Field|Description|  
      |---------------------------------|---------------------------------------|
      |**Section**|Select the valid section from lookup depending on the kind of services provided by vendor.|
      |**Concessional Code**|Select the valid concessional code from lookup depending on the kind of services provided by vendor.|
      |**Certificate No.**|Certificate number provided by the vendor can be defined to justify the lower tax deduction.|

## Set up TDS in location master

**T.A.N** needs to be defined on locations from where the company files its returns.

## Set up TDS in company information

- Following information needs to be defined in company information.

      |Field|Description|  
      |---------------------------------|---------------------------------------|
      |**T.A.N No.**|Specifies the TAN of the legal entity.|
      |**P.A.N No.**|Specifies the PAN of the legal entity.|
      |**Deductor Category**|Specifies the deductor category of the legal entity.|
      |**PAO Code**|Specifies the PAO code.|
      |**PAO Registration No.**|Specifies PAO registration number.|
      |**DDO Code**|Specifies DDO code.|
      |**DDO Registration No.**|Specifies the DDO registration number.|
      |**Ministry Type**|Specifies the Ministry type.|
      |**Ministry Code**|Specifies the Ministry code.|

## Set up TDS in state code

**State Code for eTDS/TCS** needs to be defined on States master.

## Related information

[TDS Transactions](TDS-Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
