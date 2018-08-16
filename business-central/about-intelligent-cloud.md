---
title: Intelligent Cloud | Microsoft Docs
description: Get a cloud copy of your data so you are connected to the intelligent cloud.
author: edupont04
manager: edupont

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, import, implement
ms.date: 08/16/2018
ms.author: bmeier

---

# Your access to the Intelligent Cloud with [!INCLUDE[prodlong](includes/prodlong.md)]

While [!INCLUDE[prodshort](includes/prodshort.md)] is a cloud-first service, those customers who need to run their workloads fully on premises or on the intelligent edge connected to the cloud can do so.  

When a customer signs up for [!INCLUDE[prodshort](includes/prodshort.md)], they can choose the default, cloud deployment solution, or they can choose to deploy it locally to their own choice of hardware. While they are running on their own hardware, the customer will have a tenant in the cloud, and the data from the customers hardware will be replicated to the cloud for Intelligent Cloud scenarios. At all times we’ll keep the customer informed of their *Cloud Ready* status so when they’re ready to transition to the cloud completely it’s a simple step.

We welcome these customers running their workloads on Dynamics NAV, Dynamics GP and Dynamics SL into the [!INCLUDE[prodshort](includes/prodshort.md)] fold. This is done through the same Intelligent Cloud / Intelligent Edge scenarios as for [!INCLUDE[prodshort](includes/prodshort.md)] on-premises. Each Dynamics NAV, Dynamics GP, or Dynamics SL tenant that enables the Intelligent Edge will have a [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant they can synchronize their data to. When they use this, we invoke our Intelligent Cloud scenarios of Machine Learning, Power BI, Flow, and others to drive suggested actions. This helps the customer understand further the value of [!INCLUDE[prodshort](includes/prodshort.md)], and over time, while Microsoft continues to support their Dynamics NAV, Dynamics GP, and Dynamics SL solutions, these customers can choose when they want to transition to  [!INCLUDE[prodshort](includes/prodshort.md)] as a perfect match for their businesses. Dynamics GP and Dynamics SL will continue to receive product improvements and updates, but the most benefit to these customers comes from upgrading to [!INCLUDE[prodshort](includes/prodshort.md)]. There are migration tools available within  [!INCLUDE[prodshort](includes/prodshort.md)] and AppSource, and also partners that specialize in upgrading Dynamics GP and Dynamics SL customers to [!INCLUDE[prodshort](includes/prodshort.md)].

## Making your purchase decision

When making a [!INCLUDE[prodshort](includes/prodshort.md)] purchase decision, you will have the option of
making a purchase through CSP or through DPL. If you want to make a CSP purchase but your partner is not a CSP partner, it is recommended the partner work with a Master VAR that is a CSP partner.

Users may also get started by going through the viral sign-up process and decide to purchase a license after the 30-day trial expires.  

### License purchased in CSP

Various service plans or offers are available in CSP to purchase [!INCLUDE[prodshort](includes/prodshort.md)]. Refer to [fwdlink] for additional information.  

-  |R[!INCLUDE[prodshort](includes/prodshort.md)]

  This is a ‘dual rights’ license, named user, subscription based offer that provides you with the flexibility to configure a cloud tenant, on-premise installation, or an Intelligent Cloud environment that enables you to use your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant in conjunction with your [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) installation.
  The cloud environment is set up through CSP, and the on-premises offer is set up using Order Central to obtain the FLF file. The initial purchase will be made in CSP, the order information will automatically sync with Order Central.
  This is ideal for customers that want a full cloud solution to run their business or customers that want ownership of an on-premises installation but want to take advantage of the growing services and value available in the cloud.
-  Intelligent Cloud Add-in

  This is a premium license for a [!INCLUDE[prodshort](includes/prodshort.md)] cloud solution run and managed in Microsoft Service. This is a named user, subscription-based offer, that will be available for users that have purchased their on-premises software through DPL. 
  This is ideal for customers that want to maintain ownership of an on-premises installation but want to take advantage of the growing services and value available in the cloud as well as switch from a BREP model (CAPEX) to CSP model (COPEX).

### License purchased through DPL

Various plans are available in DPL to purchase [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises, GP 2018 R2, NAV 2018, or SL 2018). Refer to [fwdlink] for additional information.  

All DPL purchases will be made through Order Central. At minimum, an Intelligent Cloud Add-In license must be purchased through CSP to create your Intelligent Cloud environment.

## Setting Up Your Intelligent Cloud

This section will provide the steps required to configure your Intelligent Cloud environment. This can simply be done by following the instructions in the Setup Intelligent Cloud assisted setup wizard.

There are a few key points that need to be understood before proceeding with the setup.

- It is always a best practice to test this configuration in your Sandbox environment before making changes to a production tenant. See [fwdlink] on how to setup your [!INCLUDE[prodshort](includes/prodshort.md)] Sandbox tenant.
- Any existing data in your [!INCLUDE[prodshort](includes/prodshort.md)] tenant will be overwritten with data from your on-premises solution, or source, once the data replication process is run. If you do not want data in your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant to be overwritten, do not configure the Intelligent Cloud environment.
- All users that do not belong to the ‘SUPER’ user group will be automatically reassigned to the Intelligent Cloud user group. This will limit them to read only access within the [!INCLUDE[prodshort](includes/prodshort.md)] tenant. See more below.
- Several stored procedures will be added to the SQL server you define. These stored procedures are required to replicate date from your SQL server to the Azure SQL server associated with your [!INCLUDE[prodshort](includes/prodshort.md)] tenant.
- With the initial release of the [!INCLUDE[prodshort](includes/prodshort.md)] Intelligent cloud, the amount of data that can be replicated for any tenant will be limited to 150GB. If your database is larger than 150GB, try reducing the number of companies you are replicating data for. Additional options for databases exceeding 150GB will be available in future updates.  
- Before setting up your Intelligent Cloud environment, ensure that at least 1 user in the system is assigned to the ‘SUPER’ user group and has SUPER permissions. This is the only user that will be allowed to make changes in the [!INCLUDE[prodshort](includes/prodshort.md)] tenant.  
- No changes will be made to users or data in your on-premises solution.

To begin configuring your Intelligent Cloud environment, navigate to the assisted setup page and launch the **Set Up Intelligent Cloud** assisted setup wizard. If you are using [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) you may also launch the wizard from your on-premises solution. You will automatically be redirected to your [!INCLUDE[prodshort](includes/prodshort.md)] online tenant to continue the configuration process.  

### Intelligent Cloud Assisted Setup

The assisted setup guide consists of up to 6 pages that take you through the process of connecting your solution to the Intelligent Cloud.  

1.   Welcome and Consent page

     This page will provide an overview of what the wizard will do. You will be asked to agree to the displayed warning message before you can continue to the next step.

2.   Product selection

     On this page, specify your source, or on-premises, solution that you are replicating data from. All supported sources will appear in the this drop down. If you don’t see your product, navigate to the **Manage Extensions** page and verify the Intelligent Cloud extension for that product is installed.

3.   SQL Connection
     If the product you selected requires a SQL connection, this page will be presented. Other source applications may require different information to connect to them. This page will display the connection information based on the product that you specified in the previous page. This is defined from the installed extensions for the product you have selected.

     *SQL Connection* There will be 2 options for SQL: SQL Server, which is your locally installed SQL Server instance or Azure SQL.

     *SQL Connection string*: If you had chosen SQL Server for your SQL Connection, you will be required to enter the connection string to your SQL Server. This information can be found [fwdlink]. This is an example of what this connection string would look like:
```
     Server=tcp:{ServerName},1433;Initial Catalog={DatabaseName};Persist Security
     Info=False;User
     ID={UserName};Password={Password};MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=True;Connection
     Timeout=30;
```
     *Integration runtime name*: This is the service that will be used to
     replicate the data from the defined source to your Business Central cloud
     tenant.

>    [!NOTE]  
>    The Integration Runtime Service is not required if your data source is Azure SQL.

>    If you are a hosting partner you may have multiple tenants running on the same Integration runtime service. Each tenant will be isolated in their own data pipeline. To add tenants to an existing integration runtime service, enter the name of the existing integration runtime service into this field. The integration runtime name can be found on the Microsoft Integration Runtime Manager. To create a new runtime service, leave the field empty, and then choose the Next button. Once you choose Next, a new replication pipeline will be created in the Azure service. This should take less than a minute to complete.

4.   Self-Hosted Integration Runtime (SHIR): This is the service will allow access to the Azure replication services to your on-premises SQL Database during the replication process. Follow the instructions on this page to install the Self Hosted Integration Service (SHIR) to a local machine.  
5.   Company Selection:

     You will be provided with a list of companies from your on-premises solution, or source. Select the companies you would like to replicate data for. If the company does not exist in your [!INCLUDE[prodshort](includes/prodshort.md)] tenant, it will be created. This process may take several minutes depending on the number of companies that need to be created.

6.   Enable & Scheduling Replication
     The final page in the wizard allows you to enable the replication process and create a schedule for when the data replication should occur. These settings are also available within your [!INCLUDE[prodshort](includes/prodshort.md)] tenant on the **Intelligent Cloud Management** page. You have the option to schedule replication daily or weekly. We recommend that you schedule your data replication for off-peak business hours.

> [!NOTE]  
>   Depending on the amount of data and your connection speed, a full replication could take several hours to complete. Subsequent replications will complete more quickly as only changed data is replicating.  

## Adding Tenant to an Exiting Runtime Service or Updating Companies

There are some scenarios where it will be necessary for you to run the Intelligent Cloud assisted set up wizard more than once.  

One example is if you want to change the companies you replicate data for. If the companies in your on-premises solution has changed; either added or deleted, or you want to change to the companies you, are replicating for, simply run the assisted setup wizard again.  

Another example of why you would want to run the wizards again, is you may be a hosting partner and want to add tenants to your existing runtime service.  

In both examples, you will be making updates to an existing runtime service. When you get to the point of the wizard where you can enter in an existing run time services name, open your Integration Runtime Service Manager application and key the value from the management page into the wizard field, you will not be allowed to copy/paste. The runtime service will identify that you are making updates to an existing service and will not create a new one.  

Complete the steps in the wizard to update the runtime service. If the change were related to adding tenants to an existing service, a new data pipeline will be created for that tenant. Changing your replication schedule or regenerating an ADF key may be done using the **Intelligent Cloud Management** page in your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant.  

## User Groups and Permission Sets 

When running in an Intelligent Cloud state, the [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant
will be, with very few exceptions, read only. Because the on-premises solution is your primary application for running your business activities such as data entry, tax reporting, sending invoices, etc. these tasks will need to be completed in the on-premises application. We limit the amount of data you can enter into your [!INCLUDE[prodshort](includes/prodshort.md)] tenant to data that is not replicated, otherwise any data that was written to the tenant database would be continuously overwritten during the replication process.  

To make setting up this ‘Read Only’ tenant for efficient, we created a new *Intelligent Cloud* user group and an *Intelligent Cloud* permission set. Once the Intelligent Cloud environment is configured, all ‘non-Super’ users will be automatically assigned the *Intelligent Cloud* user group. Only users with SUPER permissions will be allowed to make modifications to the system at this point.  

NOTE: Before configuring the Intelligent Cloud environment, ensure that at least 1 user in each company is assigned SUPER permissions.  

Users that are reassigned to the Intelligent Cloud User Group will have access to read ALL data by default. If you need to further restrict what the data a user should be able to read, the SUPER user may create new User Groups and Permissions Sets and assign users accordingly. It is highly recommended to create any new permissions sets from a copy of the Intelligent Cloud permission set and then take away permissions you do not want users to have.  

**WARNING!** If you grant insert, modify or delete permissions to any resource in the application that was set to read only, it could have a negative impact on the data in the [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant. If this occurs, you may have to clear all your data and rerun a full replication to correct this.  

## Managing your Intelligent Cloud environment

This page will provide information regarding your data replication runs over the past 30 days as well as enable you to manage your replication services.

### Viewing Replication History

Provides a view of the status of all replications that happened in the past 30 days. You will be able to view the time the replication ran, the status of each replication and when your next replication is scheduled to run.  

Replication Statistics - Tiles that will display the number of tables replicated and the number of tables that did not replicate due to errors that occurred during the replication process. You may select either tile to drill into additional details regarding the replication status of each table as well as any messaging to assist you in correcting any errors.

Replication Schedule - Enables you to set the replication schedule without having to run the assisted setup wizard again.  

Manually Running Data Migration – when selected, manually triggers data replication. Ideally, this would be used only when you received errors in the scheduled data replication, you corrected any errors, and want to push updated data to the cloud outside of a normally scheduled run.  

Clearing the [!INCLUDE[prodshort](includes/prodshort.md)] Tenant Tables – you may run into instances where you need to reset your cloud data. This option will clear all data in your cloud tenant and enable you to start over with data replication. If you need to clear data in your cloud tenant and are have connectivity issues that persist for more than 7 days, you will need to contact customer support. They will create a ticket to have your tenant data cleared.  

Regenerating a Runtime Key – if at any time you feel that your Self Hosted Integration Runtime key is no longer secure, you may select this option to regenerate a new key. A new key will be generated for you and automatically be updated in the Self Host Integration Runtime service.  

Moving to a Cloud only solution – this option will guide you through a checklist of instructions to make the full move to the cloud. Once this steps in this process are complete, data replication will be discontinued, and your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant will become your primary ERP solution.  

### Extensions

When an Intelligent Cloud environment is configured, it is highly recommended that you test the impact of any Extension in a Sandbox environment before having them installed in your production [!INCLUDE[prodshort](includes/prodshort.md)] Intelligent Cloud tenant to help avoid any data failures or untended consequences.  

### Troubleshooting Replications Errors

Now that you have purchased your license, installed any necessary software, and have applies license files, it is time to configure your solutions for Intelligent Cloud.

## System Requirements
===================

SQL 2016 or later

The database has a compatibility level 130 or higher

Dynamics 365 Business Central

Dynamics GP 2018 R2

### Viewing Intelligent Cloud Insights On-Premises
==============================================

Now that your Intelligent Cloud is up and running, you are also able to view the insights from the many cloud services within you on-premises application.  

To view Intelligent Cloud insights, navigate to the **Intelligent Cloud Insights** page. [Add more that ties into the Power Platform work and machine learning]  

## Power Platform

### Power BI

Enhancements to the current Power BI embed experience include automatic deployment of Power BI reports, default report selection, and the ability for users to manage their Power BI reports without ever requiring them to leave [!INCLUDE[prodshort](includes/prodshort.md)].  

Power BI reports will be automatically be deployed and selected upon user sign in. Once visible in Business Central, users can make edits to their Power BI reports from a new page in [!INCLUDE[prodshort](includes/prodshort.md)] that surfacing all the Power BI functionality to modify reports.  

[!INCLUDE[prodshort](includes/prodshort.md)] will also provide different default reports based upon where the data originated from. For example, if data originated from Dynamics GP, a set a default reports, specific to GP related data, will be deployed.  

A new connector will also be available for the Oct. 1 release for [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) and will require basic authentication to connect.  

### Microsoft Flow

A new connector for [!INCLUDE[prodshort](includes/prodshort.md)] will be available with the Oct. 1 release. The new connect, built on our API infrastructure, will replace the original connector built on ‘M’ Code. As part of the release of the new connector, we will support a delta service to monitor changes in data as well as expose CREATE, MODIFY and DELETE triggers when creating new Flows.  

A new connector will also be available for the Oct. 1 release for [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) and will require basic authentication to connect. This connector will not be supported in the delta service, therefore CREATE, MODIFY and DELETE triggers will not be exposed when creating a Flow.  

### PowerApps

No net new functionality will be added for the Oct. 1 release of [!INCLUDE[prodshort](includes/prodshort.md)].  

## Frequently Asked Questions

### What products and versions are supported with Intelligent Cloud?

With the initial release of the Intelligent Cloud on October 1, 2018, Dynamics GP 2018 R2 and Dynamics 365 Business Central (on-premises) will be supported. Support for additional products will become available in future updates & releases.  

### How is my on-premise data replicated to my Business Central tenant?

Data is replicated using an Azure service called Azure Data Factory (ADF). The Azure Data Factory is a service that is always running within the [!INCLUDE[prodshort](includes/prodshort.md)] cloud service manager. During the Intelligent Cloud configure process, a data pipeline is created within the ADF service that enable data to flow from your on-premises solution to your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant.  

If your data source is a local SQL Server instance, you will also be asked to configure a Self-Hosted Integration Runtime. The runtime is installed locally and enable the communication between the cloud services and your on-premise data to communicate without opening any ports or firewalls.  

### Are there any limits on the amount or type of data will replicate?

Data replication for the initial release will have a limit of 150GB. There are no restrictions on the type of data that can be replicated.  

### Is my SQL Connection string required to set up Intelligent Cloud?

Yes. The SQL Connection String is passed to Azure Data Factory where it is stored in a secure key vault. This information in required for the service to communicate with your SQL Server instance.  

### I am a hosting partner; do I need to configure the Self-Hosted Runtime Service for each tenant?

No, there is no limit on the number for tenants that can be added to Self-Hosted Integration Runtime. Each added tenant will have a dedicated pipeline created.  

### How many nodes are available in the Azure Runtime Service?

[This needs more work] You can have up to 4 nodes. Why and how?

### Will code customizations replicate?

No, only tables that is available in both your on-premises solution and your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant will replicate. Any customization would need to be made into an extension and installed on both your on-premises solution and your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant to replicate.  

### Why are my Business Central tenant permissions restricted?

Once the Intelligent Cloud is configured, all non-Delegated Admin users will be automatically assigned to the Intelligent Cloud user group. In this configuration, your on-premises solution is the master where all business entries will take place. The [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant becomes read only and the data is used to make business decisions. We restriction permissions to avoid users from accidentally entering transaction or updating master records only to have that information overwritten and lost when data replication takes place.  

### Can I ‘turn off’ my Intelligent Cloud?

You may discontinue your Intelligent Cloud environment at any point. Once you disable your Intelligent Cloud configuration, your on-premises and [!INCLUDE[prodshort](includes/prodshort.md)] tenant will become completely independent of one another.  

If you discontinued your Intelligent Cloud and want to use your [!INCLUDE[prodshort](includes/prodshort.md)] tenant as your primary solution to run and manage your business, you will need
to reassign permissions to provide read/write access to users.  

### Will my On-Premises Users and Permissions Replicate?

No, since you are not required to configure your on-premises solution with Azure Active Directory (Azure AD), we cannot guarantee a mapping between on-premises users and [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant users. [!INCLUDE[prodshort](includes/prodshort.md)] tenant users must have an Azure AD account and be manually added as users in the [!INCLUDE[prodshort](includes/prodshort.md)] tenant. All permission need to be granted in the [!INCLUDE[prodshort](includes/prodshort.md)] tenant, independent from your on-premises permissions.  

### Can I view insights from cloud services in my On-Premises solution?

Yes, a new Intelligent Cloud Insights page can be hosted within either Dynamics GP 2018 R2 or [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises). Each user will need to have a [!INCLUDE[prodshort](includes/prodshort.md)] cloud license to view the data.

### Can you export to Excel, modify the contents and import it back in? 

You can export the list to Excel but since the data is read only you cannot make changes and import it back in.

### Is the data replication only one-way?
-------------------------------------

Yes, data is only replicated from the on-premises solution to your [!INCLUDE[prodshort](includes/prodshort.md)] tenant.

### Is there a cost to configure the Intelligent Cloud?

Currently, the only costs associated with the Intelligent Cloud are your named user license costs.

### Why did my Role Center change after configuring the Intelligent Cloud?
----------------------------------------------------------------------

To keep the role center experience as clean as possible and avoid permission errors, we automatically hide actions that would generate a permission error for the user.

### Should I uninstall all my Business Central tenant Extensions?

Not necessary, most Extension will run without issue in the Intelligent Cloud environment. You may want to consider uninstalling Extensions that send data to an external service to avoid potential duplicated calls to that service. It is always a best practice to test any Extension in a Sandbox tenant configured to Intelligent Cloud.

### How do I build an Extension that enables data replication? 

The extension should be created in the same manner as any other extension. For data to replicate, you will need to add a ‘Replicate’ property to your table and set the value to \<Yes\>. If your Extension connects with an External service and you want to restrict any service calls from your [!INCLUDE[prodshort](includes/prodshort.md)] Intelligent Cloud tenant, a good practice would be to store the connection information in a separate table and set the ‘Replication’ property to \<No\>. This would enable you to keep the Extension Installed but prevent it from making any type of service calls from the Read-Only [!INCLUDE[prodshort](includes/prodshort.md)] tenant.

Once the Extension is installed in both your on-premises and [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenants, the data will begin to replicate.

### How do I find my SQL connection string?

[TBD]

### How do I find the Integration Runtime name?

[TBD]

## See Also

[Welcome to Business Central](index.md)  
[Business Central Intelligent Cloud extension](ui-extensions-intelligent-cloud.md)  
[Data Replication extension](ui-extensions-data-replication.md)  