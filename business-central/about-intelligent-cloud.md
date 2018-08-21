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
ms. search.keywords: cloud, edge
ms.date: 08/21/2018
ms.author: bmeier

---

# Your Access to the Intelligent Cloud with [!INCLUDE[prodlong](includes/prodlong.md)]

As a user of [!INCLUDE[prodshort](includes/prodshort.md)] online, you have full access to scenarios that are based on the Intelligent Cloud, such as editing data in Excel and pushing changes back to [!INCLUDE[prodshort](includes/prodshort.md)], or when you view your data in Power BI. While [!INCLUDE[prodshort](includes/prodshort.md)] is a cloud-first service, those customers who need to run their workloads fully on premises or on the intelligent edge connected to the cloud can do so.  

When a customer signs up for [!INCLUDE[prodshort](includes/prodshort.md)], they can choose the default, cloud deployment solution, or they can choose to deploy it locally to their own choice of hardware. While they are running on their own hardware, the customer will have a tenant in the cloud, and the data from the customers hardware will be replicated to the cloud for Intelligent Cloud scenarios. At all times we’ll keep the customer informed of their *Cloud Ready* status so when they’re ready to transition to the cloud completely it’s a simple step.  

For more information about connecting to the Intelligent Cloud from an on-premises deployment of [!INCLUDE[prodshort](includes/prodshort.md)], Dynamics NAV, Dynamics GP, or Dynamics SL, see [Administration and Setup for the Intelligent Cloud](/dynamics365/business-central/dev-itpro/administration/about-intelligent-edge) in the ITPro content for [!INCLUDE[prodshort](includes/prodshort.md)].  

## Making your purchase decision

When making a [!INCLUDE[prodshort](includes/prodshort.md)] purchase decision, you will have the option of
making a purchase through CSP or through DPL. If you want to make a CSP purchase but your partner is not a CSP partner, it is recommended the partner work with a Master VAR that is a CSP partner.

Users may also get started by going through the viral sign-up process and decide to purchase a license after the 30-day trial expires.  

### License purchased in CSP

Various service plans or offers are available in CSP to purchase [!INCLUDE[prodshort](includes/prodshort.md)]. Refer to [fwdlink] for additional information.  

-  [!INCLUDE[prodshort](includes/prodshort.md)]

      This is a ‘dual rights’ license, named user, subscription based offer that provides you with the flexibility to configure a cloud tenant, on-premise installation, or an Intelligent Cloud environment that enables you to use your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant in conjunction with your [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) installation.  
      The cloud environment is set up through CSP, and the on-premises offer is set up using Order Central to obtain the FLF file. The initial purchase will be made in CSP, the order information will automatically sync with Order Central.  
      This is ideal for customers that want a full cloud solution to run their business or customers that want ownership of an on-premises installation but want to take advantage of the growing services and value available in the cloud.  
-  Intelligent Cloud Add-in

      This is a premium license for a [!INCLUDE[prodshort](includes/prodshort.md)] cloud solution run and managed in Microsoft Service. This is a named user, subscription-based offer, that will be available for users that have purchased their on-premises software through DPL.  
      This is ideal for customers that want to maintain ownership of an on-premises installation but want to take advantage of the growing services and value available in the cloud as well as switch from a BREP model (CAPEX) to CSP model (COPEX).  

### License purchased through DPL

Various plans are available in DPL to purchase [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises, GP 2018 R2, NAV 2018, or SL 2018). Refer to [fwdlink] for additional information.  

All DPL purchases will be made through Order Central. At minimum, an Intelligent Cloud Add-In license must be purchased through CSP to create your Intelligent Cloud environment.

### Viewing Intelligent Cloud Insights On-Premises

Now that your Intelligent Cloud is up and running, you are also able to view the insights from the many cloud services within you on-premises application.  

To view Intelligent Cloud insights, navigate to the **Intelligent Cloud Insights** page. [Add more that ties into the Power Platform work and machine learning]  

#### Power BI

Enhancements to the current Power BI embed experience include automatic deployment of Power BI reports, default report selection, and the ability for users to manage their Power BI reports without ever requiring them to leave [!INCLUDE[prodshort](includes/prodshort.md)].  

Power BI reports will be automatically be deployed and selected upon user sign in. Once visible in Business Central, users can make edits to their Power BI reports from a new page in [!INCLUDE[prodshort](includes/prodshort.md)] that surfacing all the Power BI functionality to modify reports.  

[!INCLUDE[prodshort](includes/prodshort.md)] will also provide different default reports based upon where the data originated from. For example, if data originated from Dynamics GP, a set a default reports, specific to GP related data, will be deployed.  

A new connector will also be available for the Oct. 1 release for [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) and will require basic authentication to connect.  

#### Microsoft Flow

A new connector for [!INCLUDE[prodshort](includes/prodshort.md)] will be available with the Oct. 1 release. The new connect, built on our API infrastructure, will replace the original connector built on ‘M’ Code. As part of the release of the new connector, we will support a delta service to monitor changes in data as well as expose CREATE, MODIFY and DELETE triggers when creating new Flows.  

A new connector will also be available for the Oct. 1 release for [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) and will require basic authentication to connect. This connector will not be supported in the delta service, therefore CREATE, MODIFY and DELETE triggers will not be exposed when creating a Flow.  

## Frequently Asked Questions

### What products and versions are supported with Intelligent Cloud?

In the current version of the [!INCLUDE[prodshort](includes/prodshort.md)] Intelligent Cloud, Dynamics GP 2018 R2 and [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) are supported. Support for additional products will become available in future updates & releases.  

### How is my on-premises data replicated to my [!INCLUDE[prodshort](includes/prodshort.md)] tenant?

Data is replicated using an Azure service called Azure Data Factory (ADF). The Azure Data Factory is a service that is always running within the [!INCLUDE[prodshort](includes/prodshort.md)] cloud service manager. During the Intelligent Cloud configure process, a data pipeline is created within the ADF service that enable data to flow from your on-premises solution to your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant.  

If your data source is a local SQL Server instance, you will also be asked to configure a Self-Hosted Integration Runtime. The runtime is installed locally and enable the communication between the cloud services and your on-premise data to communicate without opening any ports or firewalls.  

### Are there any limits on the amount or type of data will replicate?

Data replication for the initial release will have a limit of 150GB. There are no restrictions on the type of data that can be replicated.  

### Is my SQL Connection string required to set up Intelligent Cloud?

Yes. The SQL Connection String is passed to Azure Data Factory where it is stored in a secure key vault. This information in required for the service to communicate with your SQL Server instance.  

### I am a hosting partner; do I need to configure the Self-Hosted Runtime Service for each tenant?

No, there is no limit on the number for tenants that can be added to Self-Hosted Integration Runtime. Each added tenant will have a dedicated pipeline created. For more information, see [Administration and Setup for the Intelligent Cloud](/dynamics365/business-central/dev-itpro/administration/about-intelligent-edge) in the ITPro content for [!INCLUDE[prodshort](includes/prodshort.md)].  

### How many nodes are available in the Azure Runtime Service?

[This needs more work] You can have up to 4 nodes. Why and how?

### Will code customization replicate?

No, only tables that is available in both your on-premises solution and your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant will replicate. Any customization would need to be made into an extension and installed on both your on-premises solution and your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant to replicate.  

### Why are my [!INCLUDE[prodshort](includes/prodshort.md)] tenant permissions restricted?

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

Yes, data is only replicated from the on-premises solution to your [!INCLUDE[prodshort](includes/prodshort.md)] tenant.

### Is there a cost to configure the Intelligent Cloud?

Currently, the only costs associated with the Intelligent Cloud are your named user license costs.

### Why did my Role Center change after configuring the Intelligent Cloud?

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
[Administration and Setup for the Intelligent Cloud](/dynamics365/business-central/dev-itpro/administration/about-intelligent-edge)  
