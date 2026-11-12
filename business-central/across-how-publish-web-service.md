---
title: Publish Business Central Objects as Web Services
description: Publish Business Central pages, queries, and codeunits as web services, find their endpoints, and verify access for authorized integrations.
author: brentholtorf
ms.topic: how-to
ai-usage: ai-assisted
ms.search.form: 810_Primary
ms.date: 11/12/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Publish Business Central objects as web services

Web services are a lightweight way to make application functionality available to different kinds of external systems and users. By default, [!INCLUDE[prod_short](includes/prod_short.md)] exposes several objects as web services for better integration with other Microsoft services. You can add other web services as your business requires.  

Publishing registers the web service, but doesn't grant access to its data or operations. The calling user or application needs permissions to run the published object and access its data. Access to metadata doesn't demonstrate permission to read or change data. Learn more in [Assign permissions to users and groups](ui-define-granular-permissions.md).

> [!IMPORTANT]
> SOAP endpoints are deprecated. Starting in Business Central version 29, Microsoft UI pages can't be published as SOAP web services. In versions 26 through 28, publishing these pages requires turning off **Feature: Disable SOAP web services on Microsoft UI pages** in **Feature Management**. SOAP services for other supported pages and codeunits are also deprecated. Use API pages and queries or OData V4 for new integrations. Learn more in [SOAP web services](/dynamics365/business-central/dev-itpro/webservices/soap-web-services).

## Create and publish a web service

The following steps explain how to create and publish a web service.  

### To create and publish a web service  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Web Services**, and then choose the related link.  
1. On the **Web Services** page, choose **New**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
1. Set **Object Type**, **Object ID**, and **Service Name** for the object you want to publish.
1. Select the check box in the **Published** column.  

> [!NOTE]
> **Codeunit** and **Page** are valid types for SOAP web services, subject to the restrictions on Microsoft UI pages. **Page** and **Query** are valid types for OData web services. Starting with version 16.3, **Codeunit** is also a valid type for OData V4 unbound actions.
> Published objects aren't specific to a company. The service URL identifies the company whose data you access.
> The service name is visible to consumers of your web service and identifies the endpoint, so choose a meaningful name.

When you publish a page or query, the **OData V4 URL** field shows its endpoint. The **SOAP URL** field shows an endpoint only when SOAP is supported for the object. For codeunits, the **OData V4 URL** field links to information about unbound actions instead of showing an endpoint.  

Copy the endpoint from the **OData V4 URL** or **SOAP URL** field for use in your integration. To test codeunits that are exposed as OData V4 unbound actions, follow the instructions in [Verifying web service availability](/dynamics365/business-central/dev-itpro/developer/devenv-creating-and-interacting-with-odatav4-unbound-action#verifying-web-service-availability).

> [!NOTE]
> The `[Scope('OnPrem')]` attribute applies to an AL method, not to an entire published web service. Developers use this attribute for methods that require APIs available only to on-premises extensions. Learn more in [Scope attribute](/dynamics365/business-central/dev-itpro/developer/methods/devenv-scope-attribute).

After you publish a web service, authenticated clients with the required permissions can access it. The following procedure illustrates how to verify its availability.  

### To verify the availability of a web service  

1. Use a client configured for the service's authentication method. For [!INCLUDE[prod_short](includes/prod_short.md)] online, use a client that sends an OAuth access token. Learn more in [Authenticate web services using OAuth](/dynamics365/business-central/dev-itpro/webservices/authenticate-web-services-using-oauth). The following table illustrates endpoint URLs for different web service types.

    > [!div class="mx-tdBreakAll"]
    > |Type|Syntax|Example|
    > |----------------|------|-------|
    > |SOAP|`https://api.businesscentral.dynamics.com/v2.0/<TenantId>/<EnvironmentName>/WS/<CompanyName>/<ObjectType>/<ServiceName>` |`https://api.businesscentral.dynamics.com/v2.0/aaaabbbb-0000-cccc-1111-dddd2222eeee/Production/WS/CRONUS%20USA%2C%20Inc./Codeunit/MyIntegration`|
    > |OData V4|`https://api.businesscentral.dynamics.com/v2.0/<TenantId>/<EnvironmentName>/ODataV4/Company('<CompanyName>')/<ServiceName>`|`https://api.businesscentral.dynamics.com/v2.0/aaaabbbb-0000-cccc-1111-dddd2222eeee/Production/ODataV4/Company('CRONUS%20USA%2C%20Inc.')/InvoiceDocument`<br/>    The company name is case-sensitive.|

1. For a page or query exposed through OData V4, send a GET request to its data URL. For a supported SOAP service, use a SOAP client to test its operations.
1. Review the response. Verify that it corresponds to the web service that you published.

When you access a web service, and you want to write data back to [!INCLUDE[prod_short](includes/prod_short.md)], you must specify the company name. You can specify the company as part of the URI as shown in the examples; alternatively, specify the company as part of the query parameters. For example, the following URIs point to the same OData web service and are both valid URIs.  

```
https://api.businesscentral.dynamics.com/v2.0/aaaabbbb-0000-cccc-1111-dddd2222eeee/Production/ODataV4/Company('CRONUS%20USA%2C%20Inc.')/Customer
```

```
https://api.businesscentral.dynamics.com/v2.0/aaaabbbb-0000-cccc-1111-dddd2222eeee/Production/ODataV4/Customer?company='CRONUS%20USA%2C%20Inc.'
```

## Related information

[Administration](admin-setup-and-administration.md)  
[Business Central Web Services for developers](/dynamics365/business-central/dev-itpro/webservices/web-services)  
[OData request limits](/dynamics365/business-central/dev-itpro/administration/operational-limits-online#ODataServices)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
