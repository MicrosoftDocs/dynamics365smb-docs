# Demo Data for Subscription Billing (Contoso)

Enable rapid onboarding and testing of Subscription Billing in Business Central by deploying comprehensive Contoso demo data. This feature provides setup, master, and transactional data to help users explore and validate core functionalities.

## Overview

The Subscription Billing demo data module allows users—especially those new to Business Central and Subscription Billing—to quickly set up a new company with realistic demo data. This includes all necessary setup, master, and transactional records, enabling hands-on evaluation and training.

## Prerequisites

- Access to the Subscription Billing module and permissions to install demo data.
- A new or test company environment in Business Central.

## Key Features

- **Comprehensive Demo Data:** Includes setup, master, and transactional data for Subscription Billing.
- **Automated Generation:** Data is created via a dedicated “Subscription Billing Module” and can be generated in full or by category (e.g., only setup data).
- **Localization Support:** Demo data can be generated for multiple countries/regions (e.g., AT, AU, BE, CA, CH, CZ, DE, DK, ES, FI, FR, GB, IS, IT, NL, NO, NZ, SE, US, W1).
- **Job Queue Integration:** Optionally creates job queue entries for Subscription Billing tasks.
- **Data Exchange and Reconciliation:** Imports data exchange definitions and reconciliation files for usage data.

## How to Use Demo Data

### 1. Install the Subscription Billing Demo Module

- Deploy the “Subscription Billing Module” in your Business Central environment.

### 2. Generate Demo Data

You can generate all demo data or only specific categories:

- **All Data:** Generates setup, master, and transactional data as defined in the provided Excel files (e.g., SC242180-Setup.xlsx, SC242180-Master.xlsx, SC242180-Transact.xlsx).
- **Setup Data Only:** Generates only setup data for initial configuration.
- **Master Data Only:** Generates only master data (e.g., customers, items).
- **Transactional Data Only:** Generates only transactional records (e.g., invoices, usage).

> **Note:** Before generating demo data, ensure that setup is completed first.

### 3. Configure Demo Data Options

On the General FastTab:

- **Create entries in Job Queue:** Specifies whether Subscription Billing tasks are created in the Job Queue (default: Yes).
- **Import Data Exchange Definition:** Imports a data exchange definition for usage data (default: Yes).
- **Import reconciliation file:** Imports a reconciliation file for usage data (default: Yes). If set to No, only usage data is created.
- **Source Code:** Sets the source code for deferral release (default: CONTDEFREL).

### 4. Localization

For supported countries/regions, demo data is generated separately to reflect local requirements.

### 5. Acceptance Criteria

When the “Additional Demo Data” option is enabled during company setup, all relevant apps and extensions with additional data are made available.

## Attachments

The following files are included for demo data generation:

| File Name                | Description                        |
|--------------------------|------------------------------------|
| SC242180-Setup.xlsx      | Setup data                         |
| SC242180-Master.xlsx     | Master data                        |
| SC242180-Transact.xlsx   | Transactional data                 |
| SC242180-All.xlsx        | All demo data combined             |
| ReconFile_Generic.csv    | Usage data reconciliation file     |
| UD-GENERIC-US.xml        | Data exchange definition           |
| ItemTemplate.xlsx        | Item template for setup            |

## Related Topics

- [Subscription Billing Setup](#)
- [Job Queue Management](#)
- [Data Exchange Definitions](#)
- [Localization in Business Central](#)
