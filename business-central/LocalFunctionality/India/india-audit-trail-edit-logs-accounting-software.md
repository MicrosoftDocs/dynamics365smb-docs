---
title: Audit Trail and Edit Logs for Accounting Software in India
description: Review audit registers, configurable change logs, and accounting record controls in Business Central for India, with historical legislation context.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: India, Indian, local, IN, English, audit trail, edit logs
ms.date: 10/21/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Audit trail and edit logs for accounting software in India

[!INCLUDE[prod_short](../../includes/prod_short.md)] provides posting registers and configurable change logs to support an audit trail. Posting registers record posted ledger activity. Change logs record selected changes to configured tables and fields; they aren't an automatic edit log of every account change.

> [!IMPORTANT]
> This article describes product capabilities and preserves a historical summary of legislation. It isn't a legal compliance assessment. Confirm current requirements, change-log configuration, permissions, retention, and service policies for your deployment. Application source code doesn't establish current legislation or cloud-service guarantees.

## Legislation

The historical legislation summary refers to principal notifications No. G.S.R. 239(E) dated March 31, 2014, No. G.S.R. 205(E) dated March 24, 2021, amendment G.S.R. 247(E) dated April 1, 2021, and amendment G.S.R. 624(E) dated August 5, 2022. The summary originally described an April 1, 2022 effective date and the following requirements. Confirm the effective dates and applicability of these notifications rather than treating that historical date as current guidance.

- Recording an audit trail of every transaction
- Creating an audit log of every change that's made in the books of accounts
- Capturing the date details about when changes are made
- Ensuring that the audit trail can't be disabled

Additionally, the rules state that the audit trail feature should meet the following conditions:

- It has been used throughout the year for all transactions that are recorded in the software.
- It hasn't been tampered with.
- The audit logs that were generated have been preserved by the company.
- The books of accounts and other relevant books and papers that are maintained in electronic mode must remain accessible in India at all times.

## Compliance

### Compliance 1: Recording an audit trail and creating an audit log

Under new guidelines of the Companies Act that specify how account books must be kept in electronic format, every company that uses accounting software to maintain its books of accounts must use only accounting software that has a feature for recording an audit trail. For compliance, the system must record and trace the data sources in the audit trail.

The read-only **G/L Registers** page shows posting batch details, including **No.**, **Created At**, **User ID**, **Source Code**, and **Journal Batch Name**. The **General Ledger** action opens the **General Ledger Entries** for the register. These records support tracing posted financial activity. They don't by themselves demonstrate compliance with every audit-log requirement.

Additionally, you can run the **Find Entries** function to show all other related entries and source documents. For more information, see [Design Details: Accounts in General Ledger](../../design-details-accounts-in-the-general-ledger.md) and [Voucher Transaction](voucher-interface-transactions.md).

For other data, use **Change Log Setup** to select tables, fields, and operations to track. Supported operations include *inserting*, *modifying*, and *deleting*. Tracking can affect performance and increase database size. Review tracked changes on **Change Log Entries**. The change log can be enabled or disabled, and its configuration and retention require administrative controls. It isn't a non-disableable log of every change. For limitations and setup guidance, see [Audit changes](../../across-log-changes.md).

> [!NOTE]
> This guideline is a general guideline and can vary, depending on the specific business scenario.

### Compliance 2: Retain books of accounts in the original format

The books of accounts and other relevant books and papers are retained in one of the following formats:

- The format that they were originally generated, sent, or received in
- A format that accurately presents the information that was generated, sent, or received

The information in the electronic records remains complete and unaltered.

Posted ledger amounts aren't edited directly on **General Ledger Entries**. Corrections use supported processes, such as reversals and correcting documents. Some supplementary information, such as an entry's **Description**, can be edited. Don't treat the read-only financial fields as proof that every field or posted document is immutable.

> [!NOTE]
> Business Central online doesn't provide customers with direct SQL access to the service database. This restriction doesn't describe on-premises deployments. APIs interact with application endpoints rather than providing direct SQL access; their validation and logging depend on the endpoint implementation.

> [!NOTE]
> Check the logging behavior of each API or extension used in your process. Don't assume that every API operation produces the same audit records as an interactive page operation.

### Compliance 3: Preserve branch transaction information

The information that's received from branch offices isn't updated and is kept as it was originally received from the branches.

Posted financial amounts can be corrected through supported processes, such as **Reverse Transaction**, credit memos, or general journals. Preservation of data sent from a branch to a head office also depends on the integration, permissions, and retention controls in use. The posting registers alone don't establish that transmitted branch data can't be changed.

### Compliance 4: Display electronic records in a legible format

Pages and reports provide ways to display electronic records. Available export formats depend on the page, report, or integration. Examples include XML, XLSX, DOCX, JSON, TXT, and PDF; not every record supports every format.

For example, **Print Voucher** on **General Ledger Entries** opens a report for the selected transaction. The [Data Exchange Framework](../../across-how-to-set-up-data-exchange-definitions.md) supports configured import and export scenarios; it isn't a universal exporter for every transaction record.

### Compliance 5: Maintain a proper system of storage for electronic records

A proper system for storing, retrieving, displaying, and printing electronic records exists. These electronic records must not be disposed of or rendered unusable, unless those actions are permitted by law. Provided that a backup of the company's books of accounts and other books and papers is maintained in electronic mode, even in a location outside India, it's kept on servers that are **physically located in India**.

[!INCLUDE[prod_short](../../includes/prod_short.md)] can be deployed into a subset of Azure datacenters. Azure is generally available in datacenters and geographical locations around the world. [!INCLUDE[prod_short](../../includes/prod_short.md)] will automatically be deployed in a defined region or datacenter where its customer data are stored. By default, **Indian companies will be deployed to the [Indian datacenters](https://dynamics.microsoft.com/availability-reports/georeport/)**. Although Microsoft might replicate data to other regions for data durability, customer data isn't replicated or moved outside the geographical location. If an Azure region-wide outage occurs, Microsoft provides business continuity and disaster recovery for the production instance of Dynamics 365 software as a service (SaaS) applications. Paired regions reside in the same geography as their enabled set to meet data residency requirements for tax and law enforcement jurisdiction purposes. For more information, see [Service overview](/dynamics365/business-central/dev-itpro/service-overview) and [Service Compliance](/dynamics365/business-central/compliance/compliance-service-compliance).

### Compliance 6: Information for filling out the annual financial statement

On an annual basis, the company provides the following information to the Registrar when it files a financial statement:

- The name of the service provider.
- The set of Internet Protocol (IP) addresses of the service provider that are used to deliver the [!INCLUDE[prod_short](../../includes/prod_short.md)] service.
- The location of the service provider, wherever applicable.
- The location where the books of accounts and other books and papers are maintained in the cloud. An example is the address that was provided by the service provider.
- The location of the service provider, if it's located outside India, and the name and address of the person who's in control of the books of account and other books and papers in India.

This information is protected by server security. We don't recommend that you include the information in any publicly available financial report. However, you can manually add this information to any specific report.

### Compliance 7: Books of accounts must remain accessible in India

Under new guidelines of the Companies Act, the books of accounts and other relevant books and papers that are maintained in electronic mode must remain accessible in India at all times, and their backup must be kept in servers that are physically located in India on a daily basis.

The following service-policy information is retained for context. Verify current availability, regional placement, backup retention, and recovery policies through the linked service documentation; these details aren't established by the India application source.

- The books of accounts and other relevant books and papers that are maintained in electronic mode in [!INCLUDE[prod_short](../../includes/prod_short.md)] are accessible in India at all times for subsequent reference.
- The Azure Geo to which a [!INCLUDE[prod_short](../../includes/prod_short.md)] environment database is deployed depends on the environment localization. Environments with Indian localization will be deployed to the [Indian datacenters](https://dynamics.microsoft.com/availability-reports/georeport/).
- Administrators of a [!INCLUDE[prod_short](../../includes/prod_short.md)] tenant can check where the database is deployed through Dynamics 365 Business Central Admin Center, by looking at the **Azure Region** field.
- Microsoft provides business continuity and disaster recovery for production instances of the [!INCLUDE[prod_short](../../includes/prod_short.md)] SaaS application if an Azure region-wide outage occurs.
- [!INCLUDE[prod_short](../../includes/prod_short.md)] maintains backups for any point-in-time up to 28 days in the past of the environment database, containing the books of accounts and other books and papers of the company that are maintained in electronic mode in [!INCLUDE[prod_short](../../includes/prod_short.md)]. Backups are kept in the same Azure Geo as the environment database.
- Administrators of a [!INCLUDE[prod_short](../../includes/prod_short.md)] tenant can't directly access or manage environment backups, because they're automatically managed by Microsoft. Administrators can also restore their environments to a specific point in time in the past by using Dynamics 365 Business Central admin center. For more information, see [Restoring an environment in the Admin center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-backup-restore).
- In the Dynamics 365 Business Central Admin Center, an administrator can view evidence about which moment [!INCLUDE[prod_short](../../includes/prod_short.md)] has successful backups from, for all dates in a given period, together with the system screenshot that indicates the default backup frequency. This data can be captured programmatically at any time using the [Get Available Restore Periods endpoint](/dynamics365/business-central/dev-itpro/administration/administration-center-api_environments#get-available-restore-periods) of the Admin Center API.
- If an administrator must export a database outside of cloud storage, they can run the **Create database** export from Dynamics 365 Business Central Admin Center at any time. In addition, administrators can access the full export history in the same Admin Center. Environment databases can be exported programmatically using the [Environment Database Export endpoints](/dynamics365/business-central/dev-itpro/administration/administration-center-api_environment_database_export) in the Admin Center API.
- If administrators of [!INCLUDE[prod_short](../../includes/prod_short.md)] delete the environment for any reason, they can recover the environment and data as needed, because it isn't permanently deleted immediately. The environment can be recovered for 28 days after deletion; the first 14 days after deletion, administrators can recover from the Admin Center, and the last 14 days this can be done by creating a support request. For more information, see [Delete and recover environments](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments-delete).

## Related information

- [Indian Local Functionalities](india-local-functionality.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
