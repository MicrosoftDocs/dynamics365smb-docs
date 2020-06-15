---
    title: Setting up Goods and Service Tax
    description: Specifies Basic Setups required

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 15/06/2020
    ms.author: v-debapd

---
# Setting up Goods and Service Tax

## Overview

Business Central has included GST Feature to Indian Localization.

**“Goods and Services Tax”** means any tax on supply of goods, or services or both except taxes on the supply of the alcoholic liquor for human consumption.

## Setting up Goods and Service Tax

### GST has two different types of setup, Auto and Manual.

### Following are the list of Auto Setups, which will be pre-configured in **Business Central - IN Localization** with help of **Tax Engine**

- Tax Types
- HSN/SAC
- Component
- Rate Setup
- Tax Rates
- Attributes


For more information about Auto Setup, see **Tax Engine** Information.

### Following are the list of Manual Setups, user need to configure these manually in **Business Central**

- GST Registration Number Setup
- Tax Accounting Period
- States
- GST Group
- GST Posting Setup
- Company Information
- Location
- General Ledger Setup
- Purchase & Payable Setup
- Sales & Receivable Setup
- Source Code Setup
- Item
- Fixed Asset
- G/L Account 
- Resource
- Item Charge
- Vendor
- Vendor Order Address
- Customer
- Customer Ship to Addresses
- Service Cost
- Bank Account

## To set up GST registration number

Registration Number under GST is called Goods and Service Tax Payer Identification Number (GSTIN). It is a state-wise PAN based 15-digit number.

1. Choose the ![img](image/search.jpg)icon, enter **GST Registration Nos.**, and then choose the related link. 
2. Fill in the fields as described in the following table.   

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**State Code**|Specify the relevant State Code of the company for which registration number has been assigned.|  
    |**Code**|Enter the valid registration number provided by authority.|  
    |**Description**|Specify the description of the registration number| 
    |**Input Service Distributor**|Specifies whether the registration belongs to a input service distributor nor not.| 

> [!TIP]
>
> State Code (GST Reg. No.) and first two digits of GST Registration Number should be same.

## To set up GST accounting period

Accounting Periods and sub-periods are created and closed here. Under GST, Fiscal year would be normally from 1st April to 31st March and Sub-Accounting Periods are months.

1. Choose the ![img](image/search.jpg)icon, enter **Tax Accounting Period**, and then choose the related link.
2. Fill in the fields as described in the following table. 

    |Field|Description|  
    |---------------------------------|---------------------------------------| 
    |**Tax Type Code**|Specify the type as **GST** to identify the accounting period.| 
    |**Starting Date**|Enter a date to specify the beginning of the period.| 
     |**Ending Date**|Enter the last date to specify the end of the period.| 
     |**Financial Year**|Specify the Financial Year of the period.| 
     |**Quarter**|Specify the different quarters of the period.|
     |**Credit Memo Locking Date**|Specify the last date by which credit memo can be entered for this period.|
     |**Annual Return Period**|Specify the last date by which annual return for GST to be filed for this period.|
     

## To set up GST states

List of State codes to be defined with relevant GST registration number state code and eTDS/TCS state code.

1.  Choose the ![img](image/search.jpg)icon, enter **States**, and then choose the related link.
2. Select **GST** and the in **Action** Tab click on **Tax Rates**.
3. Fill in the fields as described in the following table. 

    |Field|Description| 
    |---------------------------------|---------------------------------------|  
    |**Code**|Specifies the state code.| 
    |**Description**|Specifies the name of the state.|
    |**State Code (GST Reg. No.)**|Specifies the code for GST registration number.|  
    |**State Code for eTDS/TCS**|Specifies the code for eTDS/TCS.| 

## To set up GST groups

List of GST groups need to be defined, group can of two types **Goods** or **Service**.

1. Choose the ![img](image/search.jpg)icon, enter **GST Groups**, and then choose the related link.
3. Fill in the fields as described in the following table. 

    |Field|Description| 
    |---------------------------------|---------------------------------------|  
    |**Code**|Specifies the group code.| 
    |**Description**|Specifies the name of the group.|
    |**GST Group Type**|Specifies whether the group is defined as goods or service.|  
    |**Reverse Charge**|Specifies whether the group is defined as reverse charge or not.|

## To set up GST posting setup

General Ledger Account for each component and state combination is defined state-wise here.

1. Choose the ![img](image/search.jpg)icon, enter **GST Posting Setup**, and then choose the related link.
2. Fill in the fields as described in the following table.

    |Field|Description| 
    |---------------------------------|---------------------------------------|  
    |**State Code**|Specifies the state code of company which have valid GST registration number.|
    |**GST Component Code**|Specifies the relevant component code.|
    |**Receivable Account**|Specifies the general ledger account for which GST receivable amount for this state and component to be posted.|
    |**Payable Account**|Specifies the general ledger account for which GST Payable amount for this state and component to be posted.|
    |**Receivable Account (Interim)**|Specifies the general ledger account for which GST receivable interim amount for this state and component to be posted.|
    |**Payable Account (Interim)**|Specifies the general ledger account for which GST payable interim amount for this state and component to be posted.|


## To set up GST in company information

Legal entity GST registration number need to be defined

1. Choose the ![img](image/search.jpg)icon, enter **Company Information**, and then choose the related link.
2. Fill in the fields as described in the following table. 

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**State Code**|Specifies the state code of the company address|
    |**GST Registration No.**|Specifies the registration number of GST for that specified address.|
    

> [!TIP]
>
> State Code (GST Reg. No.) and first two digits of GST Registration Number should be same.

## To set up GST in location

GST registration number can be assigned to company for their multiple locations, those registration numbers can be defined in the location master

1.  Choose the ![img](image/search.jpg)icon, enter **Locations**, and then choose the related link.
2. Fill in the fields as described in the following table. 

    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**State Code**|Specifies the state code of the location address| 
    |**GST Registration No.**|Specifies the registration number of GST for that specified address.|

> [!TIP]
>
> State Code (GST Reg. No.) and first two digits of GST Registration Number should be same.

## To set up GST in general ledger setup

1. Choose the ![img](image/search.jpg)icon, enter **General Ledger Setup**, and then choose the related link.
2. Fill in the fields as described in the following table. 

    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**GST Distribution Nos.**|Specifies the number series code for distribution document.| 
    |**GST Credit Adj. Jnl Nos.**|Specifies the number series code for credit adjustment journal.|
    |**GST Settlement Nos.**|Specifies the number series code for settlement document.|
    |**GST Recon. Tolerance**|Specifies the tolerance value to be considered for GST reconciliation|  

## To set up GST in purchase and payable setup

1.  Choose the ![img](image/search.jpg)icon, enter **Purchase & Payable Setup**, and then choose the related link.
2. Fill in the required number series codes for purchase and purchase credit memo documents for different type of GST purchase transactions. for example, **Registered**, **Unregistered**.
3. Fill in the number series code for **GST liability adjustment journal**.
4. Fill in the start and end date of exemption date for reverse charge for unregistered vendor.

## To set up GST in sales and receivable setup

1.  Choose the ![img](image/search.jpg)icon, enter **Sales & Receivable Setup**, and then choose the related link.

2. Fill in the required number series codes for sales and sales credit memo documents for different type of GST sales transactions. for example, **Export**, **Debit Note**, **Non-GST** etc..

## To set up GST in source code setup

1.  Choose the ![img](image/search.jpg)icon, enter **Source Code Setup**, and then choose the related link.
2. Fill in source codes for different type of GST transaction. For **Credit Adjustment Journal**, **Settlement**, **Distribution**, **Liability Adjustment**, **Adjustment Journal**.

## To set up GST in Masters

Following are the list of masters having GST setup as defined below

- Item
- Fixed Asset
- G/L Account 
- Resource
- Item Charge

1.  Choose the ![img](image/search.jpg)icon, enter **Items**, **Fixed Asset**/**Chart of Account** > **G/L Account**/**Resources**/**Item Charges** and then choose the related link.
2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**GST Group Code**|Specifies the GST Group code relevant for the item/Fixed asset shall be selected here. GST Group codes created in GST Group Setup appears as dropdown here.|
    |**GST Credit**|Specifies the Input Tax Credit can be 'Availment' or 'Non-Availment'. This field by default displays 'Availment'. If credit cannot be availed on any item/fixed asset, then 'Non-Availment' shall be selected manually from the drop down.| 
    |**HSN/SAC Code**|Specifies HSN/SAC Codes for GST Group code selected above shall be displayed as a dropdown for this field. User has to select appropriate HSN or SAC code.| 
    |**Exempted**|This field is checked if the item is exempted from payment of tax.| 


## To set up GST in Vendor
1. Choose the ![img](image/search.jpg)icon, enter **Vendor**, and then choose the related link.

2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------|
    |**GST Vendor Type**|Vendor type can be Registered,Composite,Unregistered, Import, Exempted,SEZ. User has to select the appropriate Vendor type from the dropdown.|
    |**GST Registration No.**|Registration No. of vendor shall be entered here. Registration number is mandatory if GST Vendor Type is Registered. Registration No. shall be of 15-digits.|
    |**Associated Enterprises**|This field is activated only if GST Vendor Type is Import. This is can be used for an import transaction of services/goods from sister concerns located outside India.|
    |**Aggregate Turnover**|This field can be used only if GST Vendor Type is Unregistered, the available options are: More than 20 lakh, Less than 20 lakh. System will allow interstate supply of services if Less than 20 lakh is selected in this field for unregistered vendor.|
    |**ARN No.**|This field captures the Vendor ARN No. only when GST registration number is not available|


## To set up GST in Vendor Order Address

1. Choose the ![img](image/search.jpg)icon, enter **Vendor** > **Order Addresses**, and then choose the related link.
2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**State**|State code can be selected from dropdown for this field. User has to select appropriate State code.|
    |**GST Registration No.**|Registration No. of vendor shall be entered here. Registration number is mandatory if GST Vendor Type is Registered. Registration No. shall be of 15-digits.|
    |**ARN No.**|This field captures the Vendor ARN No. only when GST registration number is not available|

## To set up GST in Customer

1. Choose the ![img](image/search.jpg)icon, enter **Customers**, and then choose the related link.

2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**GST Customer Type**|Customer type can be Registered, Unregistered, Export, Deemed Export, SEZ Unit, SEZ Development or Exempted. User has to select the appropriate Customer type from the dropdown.|
    |**GST Registration Type**|Registration type can be GSTIN (Goods and Services Tax Payer Identification Number), UID (Unique Identification Number), and GID (Government Identification Number). Appropriate type shall be selected from the dropdown.|
    |**GST Registration No.**|The 15-digit GST Registration Number shall be entered here. Registration number is mandatory if GST Customer Type is Registered or Deemed Export.|
    |**E-Commerce Operator**|This field is activated, if sales are done through an e-commerce operator.|
    |**ARN No.**|This field captures the Vendor ARN No. only when GST registration number is not available|

## To set up GST in Customer Ship to Addresses

1. Choose the ![img](image/search.jpg)icon, enter **Customers** > **Ship to Addresses**, and then choose the related link.

2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**State**|State code can be selected from dropdown for this field. User has to select appropriate State code.|
    |**GST Registration No.**|Registration No. of vendor shall be entered here. Registration number is mandatory if GST Customer Type is Registered. Registration No. shall be of 15-digits.|
    |**ARN No.**|This field captures the Customer ARN No. only when GST registration number is not available|


## To set up GST in Service Cost

1. Choose the ![img](image/search.jpg)icon, enter **Service Cost**, and then choose the related link.

2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**GST Group Code**|Specifies the GST Group code relevant for the item/Fixed asset shall be selected here. GST Group codes created in GST Group Setup appears as dropdown here.|
    |**GST Credit**|his field is checked if the GST Credit can be Availment. This field by default displays Non- Availment.| 
    |**HSN/SAC Code**|Specifies HSN/SAC Codes for GST Group code selected above shall be displayed as a dropdown for this field. User has to select appropriate HSN or SAC code.| 
    |**Exempted**|This field is checked if the item is exempted from payment of tax.| 


## To set up GST in Bank Account

1. Choose the ![img](image/search.jpg)icon, enter **Bank Account**, and then choose the related link.
2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**State Code**|This field is required for GST calculation in Bank Charges transactions.|
    |**GST Registration Status**|GST Registration type can be Blank or Registered. If GST registration No. is added in Bank Account Master the status will be updated as Registered.|
    |**GST Registration No.**|Registration No. of Bank shall be entered here. Registration number is mandatory, if GST Registration Status is Registered. Registration No. comprises 15-digits.|

























