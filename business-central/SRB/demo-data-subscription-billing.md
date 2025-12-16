---
title: Contoso demo data
description: Create and use demo data for subscription billing.
author: TobiSIT
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 5194,
ms.date: 12/16/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Contoso demo data for Subscription Billing

Subscription Billing supports Contoso demo data. The Contoso demo data for Subscription Billing helps users, and especially those who are new to Business Central and Subscription Billing, to quickly set up a new company with realistic demo data. The data includes the setup, master, and transactional records you need for onboarding, and enables hands-on evaluation and training.

## Prerequisites

- Access to the Subscription Billing module and permissions to set up demo data.
- A new or test company environment in Business Central.

## Key Features

- **Comprehensive Demo Data:** Generate a rich set of demo data that includes setup, master, and transactional data for Subscription Billing.
- **Automated Generation:** Create the data by using the **Subscription Billing Demo Data** app, which you can get on Microsoft AppSource. You can generate demo data in full, or just the basic setup data.
- **Localization Support:** Generate demo data for multiple countries/regions (for example, AT, AU, BE, CA, CH, CZ, DE, DK, ES, FI, FR, GB, IS, IT, NL, NO, NZ, SE, US, W1).
- **Job Queue Integration:** Optionally, create job queue entries for Subscription Billing tasks.
- **Data Exchange and Reconciliation:** Import data exchange definitions and reconciliation files for usage data.

## How to use the demo data

### 1. Install the Subscription Billing Demo Data app frin AppSource

- Deploy the **Subscription Billing Demo Data** app in your Business Central environment. The app is available on Microsoft AppSource.

### 2. Generate the demo data

Like the other areas that the Contoso demo data supports, you can generate all demo data or setup data only:

- **Generate:** Generates setup, master, and transactional data.
- **Generate Setup Data:** Generates only setup data for initial configuration.

> **Note:** Before you generate demo data, ensure that basic setup is completed first.

### 3. Configure demo data options

For the Subscription Billing module, use the **Configure** action to prepare the module:

- **Create entries in Job Queue**: Specifies whether Subscription Billing tasks are created in the job queue. By default, this option is turned on.
- **Import Data Exchange Definition:** Imports a data exchange definition for usage data. By default, this option is turned on.
- **Import reconciliation file:** Imports a reconciliation file for usage data. By default, this option is turned on. If you turn off this option, only usage data is created.

### 4. Localization

For supported countries/regions, demo data is generated separately to reflect local requirements.

## Related Topics

[Contoso Coffee Demo Data](https://learn.microsoft.com/en-us/dynamics365/business-central/contoso-coffee/contoso-coffee-intro?wt.mc_id=d365bc_inproduct_helppane)  
[Job Queue Management](#)  
[Data Exchange Definitions](#)  
