---
title: Contoso Demo Data
description: Create and use demo data for subscription billing.
author: TobiSIT
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 5194,
ms.date: 07/16/2025
ms.service: dynamics-365-business-central
---

# Demo Data for Subscription Billing (Contoso)

Subscription Billing supports Contoso demo data. Herewith it enables rapid onboarding and testing of Subscription Billing in Business Central by deploying comprehensive Contoso demo data. This feature provides setup, master, and transactional data to help users explore and validate core functionalities.

## Overview

The Subscription Billing demo data allows users — especially those new to Business Central and Subscription Billing — to quickly set up a new company with realistic demo data. This includes all necessary setup, master, and transactional records, enabling hands-on evaluation and training.

## Prerequisites

- Access to the Subscription Billing module and permissions to set up demo data.
- A new or test company environment in Business Central.

## Key Features

- **Comprehensive Demo Data:** Includes setup, master, and transactional data for Subscription Billing.
- **Automated Generation:** Data is created via a dedicated “Subscription Billing Demo Data” app available on Microsoft AppSource for Business Central. Demo data can be generated in full or setup data only.
- **Localization Support:** Demo data can be generated for multiple countries/regions (e.g., AT, AU, BE, CA, CH, CZ, DE, DK, ES, FI, FR, GB, IS, IT, NL, NO, NZ, SE, US, W1).
- **Job Queue Integration:** Optionally creates job queue entries for Subscription Billing tasks.
- **Data Exchange and Reconciliation:** Imports data exchange definitions and reconciliation files for usage data.

## How to Use Demo Data

### 1. Install Subscription Billing Demo Data app

- Deploy the “Subscription Billing Demo Data” app in your Business Central environment. The app is available on Microsoft AppSource for Business Central.

### 2. Generate Demo Data

As for the other areas supported by Contoso demo data, you can generate all demo data or setup data only:

- **Generate:** Generates setup, master, and transactional data.
- **Generate Setup Data:** Generates only setup data for initial configuration.

> **Note:** Before generating demo data, ensure that basic setup is completed first.

### 3. Configure Demo Data Options

For Subscription Billing module, use “Configure” action to prepare the module:

- **Create entries in Job Queue:** Specifies whether Subscription Billing tasks are created in the Job Queue (default: Yes).
- **Import Data Exchange Definition:** Imports a data exchange definition for usage data (default: Yes).
- **Import reconciliation file:** Imports a reconciliation file for usage data (default: Yes). If set to No, only usage data is created.

### 4. Localization

For supported countries/regions, demo data is generated separately to reflect local requirements.

## Related Topics

- [Contoso Coffee Demo Data](https://learn.microsoft.com/en-us/dynamics365/business-central/contoso-coffee/contoso-coffee-intro?wt.mc_id=d365bc_inproduct_helppane)
- [Job Queue Management](#)
- [Data Exchange Definitions](#)
