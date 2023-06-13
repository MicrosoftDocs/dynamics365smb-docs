---
    title: Audit trail and edit logs for accounting software in India
    description: This article provides information about the new Indian tax and companies legislation guidelines for accounting software. 
    author: altotovi
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, Indian, local, IN, English
    ms.date: 06/09/2023
    ms.author: altotovi

---

# Audit trail and edit logs for accounting software in India 

[!INCLUDE[prod_short](../../includes/prod_short.md)] complies with the new Indian tax legislation guidelines for accounting software to record an audit trail of all transactions. An edit log is also created for each change made to an account. This log records the date when the change was made.  

## The legislation  

Principal notifications No. G.S.R. 239(E) dated March 31, 2014, No. G.S.R. 205(E) dated March 24, 2021, amended vide notification G.S.R. 247(E) dated April 1, 2021, and amendment notification G.S.R. 624(E) dated August 5, 2022, states that, as of April 1, 2022, all businesses that use accounting software to maintain books of accounts should have an audit trail feature that includes the following functionality: 

- Recording an audit trail of every transaction.   
- Creating an audit log of every change made in the books of accounts.
- Capturing the date details of when changes are made.
- Ensuring that the audit trail can't be disabled.

Additionally, the rules state that the audit trail feature should meet the following conditions:  

- It's been used throughout the year for all transactions that are recorded in the software.
- It hasn't been tampered with.
- The audit logs generated have been preserved by the company.
- The books of account and other relevant books and papers maintained in electronic mode shall remain accessible in India at all times.

## Compliance  

### Compliance 1: Recording an audit trail and creating an audit log 

Under new guidelines of the Companies Act that specify how account books must be kept in electronic format, every company that uses accounting software to maintain its books of accounts must only use accounting software that has a feature for recording an audit trail. The system must record and trace the data sources in the audit trail for compliance.

[!INCLUDE[prod_short](../../includes/prod_short.md)] is fully compliant with the requirement to record accounting data. The **G/L Registers** page provides details about each transaction with the register number, creation date and time, user ID of who created this transaction, and its source code. The **General Ledger** function on the **G/L Register** fetches the financial transaction entries posted in the general ledger. The function opens the **General Ledger Entries** page related to specific **G/L Register**, which shows transaction details. 

Additionally, you can run the **Find Entries** function to show all other related entries and source documents. For more information, see [Design Details: Accounts in General Ledger](../../design-details-accounts-in-the-general-ledger.md) and [Voucher Transaction](voucher-interface-transactions.md).

For other data, you can track specific types of changes to tables and fields with the **Change Log** function. Changes that can be tracked include *inserting*, *modifying*, and *deleting* key operations. When you enable a tracking change for any table, note that the impact on performance might vary depending on the table's category, but it can also increase the database's size. When you track change for a table or field, a record of every change to that table or field is stored on the **Change Log Entries** page. You can use this feature to track changes in any data in the system. For example, companies that use [!INCLUDE[prod_short](../../includes/prod_short.md)] to maintain books of accounts are fully compliant with the new notifications and can track transaction data to the source. For more information, see [Auditing Changes in Business Central](../../across-log-changes.md).

> [!NOTE]
> This guideline is a general guideline and may vary depending on the specific business scenario.

### Compliance 2: Retain books of accounts in the original format

The books of accounts and other relevant books and papers are retained in one of the following formats: 

- The format in which they were originally generated, sent, or received.  
- A format that accurately presents the information generated, sent, or received.

The information in the electronic records will remain complete and unaltered. 

Transactions posted at [!INCLUDE[prod_short](../../includes/prod_short.md)] remain complete, and in the format, they were initially generated in. Therefore, [!INCLUDE[prod_short](../../includes/prod_short.md)] includes no process for changing the format or content of a posted transaction. 

### Compliance 3: Preserve branch transactions information

The information received from branch offices isn't updated and is kept as it was originally received from the branches. 

In [!INCLUDE[prod_short](../../includes/prod_short.md)], changes can't be made to posted financial data. Therefore, financial transactions can't be edited after they are posted. However, they can be reversed using the **Reverse Transaction** function. Data that is sent from a branch to a head office can't be changed by the head office. However, you can adjust the posted transaction through the specified mode of the transaction, such as a credit memo or general journal, that was posted in the ledger of both the branch and the head office.  

### Compliance 4: Display electronic records in a legible format 

The information in the electronic record of the document is shown in [!INCLUDE[prod_short](../../includes/prod_short.md)]. [!INCLUDE[prod_short](../../includes/prod_short.md)] enables at least one output component per file. Typically, [!INCLUDE[prod_short](../../includes/prod_short.md)] contains multiple file output components of different types. For example, XML, XLSX, DOCX, JSON, TXT, or PDF. 

[!INCLUDE[prod_short](../../includes/prod_short.md)] guarantees that at least every transaction record can be exported or opened in Microsoft Excel format. By using a configurator in the **[Data Exchange Framework](../../across-how-to-set-up-data-exchange-definitions.md)**, users can define which file format to use for specific entries. 

### Compliance 5: Maintain a proper system of storage for electronic records

A proper system for storing, retrieving, displaying, and printing electronic records exists. These electronic records must not be disposed of or rendered unusable unless those actions are permitted by law. Provided that a backup of the company's books of accounts and other books and papers is maintained in electronic mode, even in a location outside India, it will be kept on servers physically located in India. 

[!INCLUDE[prod_short](../../includes/prod_short.md)] can be deployed into a subset of Azure data centers. Azure is generally available in data centers and geographical locations around the world. [!INCLUDE[prod_short](../../includes/prod_short.md)] will be automatically deployed in a defined region or data center where their customer data will be stored, and Indian companies will be deployed to the [Indian data centers by default](https://dynamics.microsoft.com/en-us/availability-reports/georeport/). Although Microsoft might replicate data to other regions for data durability, customer data isn't replicated or moved outside the geographical location. If an Azure region-wide outage occurs, Microsoft provides business continuity and disaster recovery for Dynamics 365 software as a service (SaaS) applications production instance. Paired regions reside within the same geography as their enabled set to meet data residency requirements for tax and law enforcement jurisdiction purposes. For more information, see [Service overview](/dynamics365/business-central/dev-itpro/service-overview), and [Service Compliance](/dynamics365/business-central/compliance/compliance-service-compliance).   

### Compliance 6: Information for filling out the annual financial statement

On an annual basis, the company will provide the following information to the Registrar when it files a financial statement:

- The name of the service provider.   
- The set of Internet Protocol (IP) addresses of the service provider used for delivering [!INCLUDE[prod_short](../../includes/prod_short.md)] service.  
- The location of the service provider, wherever applicable.  
- The location where the books of accounts and other books and papers are maintained in the cloud. Gor example, the address that was provided by the service provider.  
- The location of the service provider if it's located outside India and the name and address of the person in control of the books of account and other books and papers in India.  

This information is protected by server security. We don't recommend including the information in any publicly available financial report. However, you can manually add this information to any specific report.  

### Compliance 7: Books of accounts shall remain accessible in India 

Under new guidelines of the Companies Act which specify that the books of account and other relevant books and papers maintained in electronic mode shall remain accessible in India at all times, and their back-up shall be kept in servers physically located in India on a daily basis. 

[!INCLUDE[prod_short](../../includes/prod_short.md)] is fully compliant with the requirements: 

* The books of account and other relevant books and papers maintained in electronic mode in [!INCLUDE[prod_short](../../includes/prod_short.md)] are accessible in India at all times for subsequent reference. 
* [!INCLUDE[prod_short](../../includes/prod_short.md)] provides that the backup of the books of account and other books and papers of the company maintained in electronic mode in [!INCLUDE[prod_short](../../includes/prod_short.md)] are kept in servers physically located in India on a daily basis. 
* [!INCLUDE[prod_short](../../includes/prod_short.md)] is automatically deployed in a defined region or data center where customer data will be stored, and Indian companies will be deployed to the [Indian data centers by default](https://dynamics.microsoft.com/en-us/availability-reports/georeport/). Although Microsoft might replicate data to other regions for data durability, customer data won't be replicated or moved outside the geographical location. 
* Administrators of a [!INCLUDE[prod_short](../../includes/prod_short.md)] tenant can check where the database is deployed through **Dynamics 365 Business Central admin center**, looking at the information in the **Azure Region** field.  
* Microsoft provides business continuity and disaster recovery for [!INCLUDE[prod_short](../../includes/prod_short.md)] software production instances as a service (SaaS) application if an Azure region-wide outage occurs. 
* Databases are protected by automatic backups that are kept for 28 days. The backup includes data from the database's production and sandbox environments. Administrators of a [!INCLUDE[prod_short](../../includes/prod_short.md)] tenant can't directly access or manage these backups because they're managed automatically by Microsoft. In **Dynamics 365 Business Central admin center**, the administrator can see evidence from which moment [!INCLUDE[prod_short](../../includes/prod_short.md)] has successful backups for all dated in given period together with the system screenshot indicating default backup frequency. Administrators can also restore their environments to a specific point in time in the past using **Dynamics 365 Business Central admin center** as mentioned. For more information, see [Restoring an environment in the Admin center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-backup-restore). 
* If an administrator needs to export a database outside of cloud storage, they can do it anytime by running the **Create database** export from **Dynamics 365 Business Central admin center**. In addition, administrators can access the full export history in the same admin center. 
* If administrators of [!INCLUDE[prod_short](../../includes/prod_short.md)] delete the environment for any reason, they can recover this environment and data if needed, because it isn't permanently deleted immediately. The environment can be recovered during a retention period that lasts seven days. For more information, see [Delete and recover environments](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments-delete). 


## See also

* [Indian Local Functionalities](india-local-functionality.md)
* [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
