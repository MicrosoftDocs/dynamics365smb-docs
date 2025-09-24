---
title: Setting up Goods and Service Tax
description: Describes the essential steps for basic GST setup in Business Central for India.
author: v-debapd 
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST setup, GST rates setup, GST registration number setup, States setup, tax accounting period, GST groups, HSN/SAC, GST posting setup, GST company information, GST on location, GST general ledger setup, GST purchase payable setup, GST on source code setup, GST on vendor, GST on vendor order address, GST on customer, GST on customer ship to addresses, GST on service cost, GST on bank account
ms.date: 06/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up goods and services tax

Business Central has included GST Feature to Indian Localization.

**“Goods and Services Tax”** means any tax on supply of goods, or services or both except taxes on the supply of the alcoholic liquor for human consumption.

It's a destination-based tax on consumption of goods and services. It's levied at all stages from manufacture up to final consumption with credit of taxes paid at previous stages available as set off. Briefly, only value addition is taxed and burden of tax is to be borne by the final consumer.

GST is a comprehensive tax levy on manufacture, sale, and consumption of goods and services at a national/regional level. It has subsume indirect taxes like excise duty, countervailing duty and service tax, as also state levies like Value Added Tax, Octroi, Entry Tax, Luxury Tax, etc.

## Process

GST has two different types of setups, Automatic and Manual.

The following is the list of Automatic Setups that are pre-configured with the help of Tax Engine

- Tax Types
- Component
- Rate Setup
- Attributes

For more information about Automatic Setup, see **Tax Engine** information.

The following is the list of Manual Setups that are required to be configured manually

- [GST Rate](gst-001-basic-setup.md#set-up-gst-rates)
- [GST Registration Number](gst-001-basic-setup.md#set-up-gst-registration-number)
- [Tax Accounting Period](gst-001-basic-setup.md#set-up-tax-accounting-period)
- [States](gst-001-basic-setup.md#set-up-states)
- [GST Groups](gst-001-basic-setup.md#set-up-gst-groups)
- [HSN/SAC](gst-001-basic-setup.md#set-up-hsnsac)
- [GST Posting Setup](gst-001-basic-setup.md#set-up-gst-posting-setup)
- [GST on Company Information](gst-001-basic-setup.md#set-up-gst-on-company-information)
- [GST on Location](gst-001-basic-setup.md#set-up-gst-on-location)
- [GST on General Ledger Setup](gst-001-basic-setup.md#set-up-gst-on-general-ledger-setup)
- [GST on Purchase and Payable Setup](gst-001-basic-setup.md#set-up-gst-on-purchase-and-payable-setup)
- [GST on Source Code Setup](gst-001-basic-setup.md#set-up-gst-on-source-code-setup)
- [GST on Masters](gst-001-basic-setup.md#set-up-gst-on-masters)
- [GST on Vendor](gst-001-basic-setup.md#set-up-gst-on-vendor)
- [GST on Vendor Order Address](gst-001-basic-setup.md#set-up-gst-on-vendor-order-address)
- [GST on Customer](gst-001-basic-setup.md#set-up-gst-on-customer)
- [GST on Customer Ship to Addresses](gst-001-basic-setup.md#set-up-gst-on-customer-ship-to-addresses)
- [GST on Service Cost](gst-001-basic-setup.md#set-up-gst-on-service-cost)
- [GST on Bank Account](gst-001-basic-setup.md#set-up-gst-on-bank-account)

## Set up GST rates

Rate of GST is defined in combination of HSN/SAC, group, and states.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Type** > **GST** > **Action** > **Tax Rates**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**HSN/SAC**|Specifies the HSN/SAC code.|
    |**GST Group Code**|Specifies the GST group code.|
    |**From State**|Specifies the vendor state code.|
    |**Location State Code**|Specifies the location state code.|
    |**Date From**|Specifies the starting date.|
    |**Date To**|Specifies the ending date.|
    |**SGST %**|Specifies the SGST rate.|
    |**CGST %**|Specifies the CGST rate.|
    |**IGST %**|Specifies the IGST rate.|
    |**Cess %**|Specifies the Cess rate.|
    |**KFC %**|Specifies the KFC rate.|
    |**POS Out of India**|Specifies whether **POS out of India** functionality is activated or not.|
    |**POS as Vendor State**|Specifies whether **POS as Vendor State** functionality is activated or not.|

## Set up GST registration number

Registration Number under GST is called Goods and Service Tax Payer Identification Number (GSTIN). It's a state-wise PAN based 15-digit number.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Registration Nos.**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**State Code**|Specify the relevant State Code of the company for which registration number has been assigned.|  
    |**Code**|Enter the valid registration number provided by authority.|  
    |**Description**|Specify the description of the registration number.|
    |**Input Service Distributor**|Specifies whether the registration belongs to an input service distributor nor not.|

> [!TIP]
>
> State Code (GST Reg. No.) and first two digits of GST Registration Number should be same.

## Set up tax accounting period

Accounting Periods and sub-periods are created and closed here. Under GST, Fiscal year would be normally from 1st April to 31st March and Sub-Accounting Periods are months.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Accounting Period**, and then choose the related link.
1. Fill in the fields as described in the following table. 

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Tax Type Code**|Specify the type as **GST** to identify the accounting period.|
    |**Starting Date**|Enter a date to specify the beginning of the period.|
     |**Ending Date**|Enter the last date to specify the end of the period.|
     |**Financial Year**|Specify the Financial Year of the period.|
     |**Quarter**|Specify the different quarters of the period.|
     |**Credit Memo Locking Date**|Specify the last date by which credit memo can be entered for this period.|
     |**Annual Return Period**|Specify the last date by which annual return for GST has to be filed for this period.|

## Set up states

List of State codes to be defined with relevant GST registration number state code and eTDS/TCS state code.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **States**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**Code**|Specifies the state code.|
    |**Description**|Specifies the name of the state.|
    |**State Code (GST Reg. No.)**|Specifies the code for GST registration number.|  
    |**State Code for eTDS/TCS**|Specifies the code for eTDS/TCS.|

## Set up GST groups

List of GST groups need to be defined. A group can be of two types **Goods** or **Service**.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Groups**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**Code**|Specifies the group code.|
    |**Description**|Specifies the name of the group.|
    |**GST Group Type**|Specifies whether the group is defined as goods or service.|  
    |**GST Place of Supply**|Specifies GST place of supply of the GST group.|
    |**Reverse Charge**|Specifies whether the group is defined as reverse charge or not.|

## Set up HSN/SAC

List of HSN/SAC codes against relevant GST groups need to be defined.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **HSN/SAC**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**GST Group Code**|Specifies the GST group code.|
    |**Code**|Specifies the HSN/SAC code.|
    |**Description**|Specifies the description of the HSN/SAC code.|
    |**Type**|Specifies the type of the HSN/SAC code, e.g HSN, SAC.|

## Set up GST posting setup

General Ledger Account for each component and state combination is defined state-wise.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**State Code**|Specifies the state code of company that have valid GST registration number.|
    |**GST Component Code**|Specifies the relevant component code.|
    |**Receivable Account**|Specifies the general ledger account for which GST receivable amount for this state and component is to be posted.|
    |**Payable Account**|Specifies the general ledger account for which GST Payable amount for this state and component is to be posted.|
    |**Receivable Account (Interim)**|Specifies the general ledger account for which GST receivable interim amount for this state and component is to be posted.|
    |**Payable Account (Interim)**|Specifies the general ledger account for which GST payable interim amount for this state and component is to be posted.|
    |**Expense Account**|Specifies the general ledger account for which GST expense amount for this state and component is to be posted.|
    |**Refund Account**|Specifies the general ledger account for which GST refund amount for this state and component is to be posted.|
    |**Receivable Acc. Interim (Dist.)**|Specifies the general ledger account for which GST distribution for receivable interim amount for this state and component is to be posted.|
    |**Receivable Acc (Dist.)**|Specifies the general ledger account for which GST distribution receivable amount for this state and component is to be posted.|
    |**GST Credit Account**|Specifies the general ledger account for which GST credit amount for this state and component is to be posted.|
    |**GST TDS Receivable Account**|Specifies the general ledger account for which GST TDS receivable amount for this state and component is to be posted.|
    |**GST TCS Receivable Account**|Specifies the general ledger account for which GST TCS receivable amount for this state and component is to be posted.|
    |**GST TCS Payable Account**|Specifies the general ledger account for which GST TCS payable amount for this state and component is to be posted.|
    |**IGST Payable A/c (Import))**|Specifies the general ledger account for which GST import payable amount for this state and component is to be posted.|

## Set up GST on company information

Legal entity's GST registration number needs to be defined.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.
1. Fill in the fields as described in the following table. 

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**State Code**|Specifies the state code of the company address.|
    |**GST Registration No.**|Specifies the registration number of GST for the specified address.|
    |**ARN No.**|Capture the ARN No. only when GST registration number isn't available.|

> [!TIP]
>
> State Code (GST Reg. No.) and first two digits of GST Registration Number should be same.

## Set up GST on location

GST registration number can be assigned to company for their multiple locations. These registration numbers can be defined in the location master.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**State Code**|Specifies the state code of the location address.|
    |**GST Registration No.**|Specifies the registration number of GST for the specified address.|
    |**Location ARN No.**|Capture the ARN No. only when GST registration number isn't available.|
    |**GST Input Service Distributor**|Specifies whether the location is registered as an input service distributor or not.|
    |**Bonded warehouse**|Specifies whether the location is treated as bonded warehouse or not.|

> [!TIP]
>
> State Code (GST Reg. No.) and first two digits of GST Registration Number should be same.

## Set up GST on general ledger setup

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**State Code - Kerala**|Specifies state code Kerala.|
    |**GST Distribution Nos.**|Specifies the number series code for distribution document.|
    |**GST Credit Adj. Jnl Nos.**|Specifies the number series code for credit adjustment journal.|
    |**GST Settlement Nos.**|Specifies the number series code for settlement document.|
    |**GST Recon. Tolerance**|Specifies the tolerance value to be considered for GST reconciliation.|  
    |**Custom Duty Component Code**|Specifies the custom duty component code.|
    |**GST Opening Account**|Specifies the account, which is used for opening transaction of GST.|

## Set up GST on purchase and payable setup

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase & Payable Setup**, and then choose the related link.
1. Enter exemption's start and end date for reverse charge for unregistered vendor in **RCM Exempt Start Date (Unreg)** and **RCM Exempt End Date (Unreg)**

## Set up GST on source code setup

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Source Code Setup**, and then choose the related link.
1. Fill in source codes for different types of GST transactions. For **Credit Adjustment Journal**, **Settlement**, **Distribution**, **Liability Adjustment**, **Adjustment Journal**.

## Set up GST on masters

The following is the list of masters requiring setup of GST

- Item
- Fixed Asset
- G/L Account
- Resource
- Item Charge

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Items**, **Fixed Asset**, **Chart of Account** > **G/L Account**, **Resources**, and **Item Charges** and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**GST Group Code**|Specifies the GST Group code that is relevant for the Item, Fixed asset, G/L Account, Resources, or Item Charges. GST Group codes created in GST Group Setup appear as dropdown.|
    |**GST Credit**|Specifies that Input Tax Credit can be 'Availment' or 'Non-Availment'. This field by default displays 'Availment'. If credit can't be availed on any Item, Fixed Asset, G/L Account, Resources and Item Charge, then 'Non-Availment' shall be selected manually from the drop-down.|
    |**HSN/SAC Code**|Specifies HSN/SAC Code for the GST Group selected in GST Group code field.
    |**Exempted**|This field is checked if the item is exempted from payment of tax.|

1. For Price Inclusive of Tax setup go to **Items** > **Prices & Discount** > **Sales Price** and fill the following information

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**Unit Price**|Specifies the unit price of the item.|
    |**Price Inclusive of Tax**|Specifies whether the unit price of the item is inclusive of tax or not.|

## Set up GST on vendor

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Vendor**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**GST Vendor Type**|Vendor type can be Registered, Composite, Unregistered, Import, Exempted, SEZ. It has to be selected from the dropdown.|
    |**GST Registration No.**|Enter Registration No. of vendor. Registration number is mandatory if GST Vendor Type is Registered. Registration No. is of 15-digits.|
    |**Associated Enterprises**|This field is activated only if GST Vendor Type is Import. This can be used for an import transaction of services or goods from sister concerns located outside India.|
    |**Aggregate Turnover**|Applicable only if GST Vendor Type is Unregistered. The available options are: More than 20 lakh, Less than 20 lakh. System allows interstate supply of services if Less than 20 lakh is selected in this field for unregistered vendor.|
    |**ARN No.**|Capture the Vendor ARN No. only when GST registration number isn't available.|

## Set up GST on vendor order address

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Vendor** > **Order Addresses**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**State**|State code can be selected from dropdown for this field. appropriate State code has to be selected.|
    |**GST Registration No.**|Enter Registration No. of vendor. Registration number is mandatory if GST Vendor Type is Registered. Registration No. is of 15-digits.|
    |**ARN No.**|Capture the Vendor ARN No. only when GST registration number isn't available.|

## Set up GST on customer

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**GST Customer Type**|Customer type can be Registered, Unregistered, Export, Deemed Export, SEZ Unit, SEZ Development or Exempted. Select the appropriate Customer type from the dropdown.|
    |**GST Registration Type**|Registration type can be GSTIN (Goods and Services Tax Payer Identification Number), UID (Unique Identification Number), and GID (Government Identification Number). Appropriate type shall be selected from the dropdown.|
    |**GST Registration No.**|Enter the 15-digit GST Registration Number. Registration number is mandatory if GST Customer Type is Registered or Deemed Export.|
    |**E-Commerce Operator**|This field is activated, if sales are done through an e-commerce operator.|
    |**ARN No.**|Capture the Customer ARN No. only when GST registration number isn't available.|

## Set up GST on customer ship to addresses

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Customers** > **Ship to Addresses**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**State**|Select state from the dropdown for this field. Select appropriate State code.|
    |**GST Registration No.**|Enter Registration No. of customer. Registration number is mandatory if GST Customer Type is Registered. Registration No. is of 15-digits.|
    |**ARN No.**|Capture the Customer ARN No. only when GST registration number isn't available.|

## Set up GST on service cost

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Service Cost**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**GST Group Code**|Specifies the GST Group code relevant for the service cost. GST Group codes created in GST Group Setup appear as dropdown.|
    |**GST Credit**|Check if the GST Credit can be Availment or Non-Availment. By default this field displays Availment.|
    |**HSN/SAC Code**|Specifies HSN/SAC Code for the GST Group selected in GST Group code field.| 
    |**Exempted**|Check if the item is exempted from payment of tax.|

## Set up GST on bank account

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Account**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**State Code**|Required for GST calculation in Bank Charges transactions.|
    |**GST Registration Status**|Can be Blank or Registered. If GST registration No. is added in Bank Account Master the status is updated as Registered.|
    |**GST Registration No.**|Enter Registration No. of Bank. Registration number is mandatory, if GST Registration Status is Registered. Registration No. comprises 15-digits.|

## Related information

[Purchase from Composite Vendor](GST-Purchase-from-Composite-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
