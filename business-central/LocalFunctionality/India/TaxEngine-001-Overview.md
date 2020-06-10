---
    title: Tax Engine Overview
    description: Tax Engine Overview

---
# Tax Engine Overview

Tax Engine is a suite of extensions to automate tax calculation based on certain rules and conditions. Use cases pertaining to a tax type can be defined. Use case will have the description of business scenario, conditions which need to be met and event which will trigger the calculation of tax. A use case can be enabled or disabled as per the business need.

> [!NOTE]
> The Tax engine functionality is only available for legal entities with a primary address in India.


Tax Engine consists of six different extensions. Extensions are packaged to deliver unit functionality related to configuration of tax, tax calculation, import and export of configuration etc.

### Core

Core extension contains the UI elements and related tables which are commonly used throughout Tax Engine. Also, it has library functions available which can be used by any other extension other than Tax Engine to get any value. 

### Scripting

Script extension contains UI elements and related tables which are used in scripting of Business logics within a use case.

### Tax Type Handler

Tax Type Handler extension contains UI elements and related tables which are helpers for configuring a business use case.

### Tax Use Case Handler

Tax Use Case Handler extension contains UI elements and related tables which can be used for configuring a business use case. A use case can only be configured for single tax entity with the help of elements created in “Tax Type Handler” as inputs.

### Tax Posting Handler

Posting Handler extension contains UI elements and related tables which can be used for configuring posting of tax components to G/L Accounts and related tax ledgers.


### Json Exchange

Json Exchange extension will be used where there is a need to import or export the configuration data of tax engine as json.







































