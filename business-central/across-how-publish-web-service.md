---
title: Expose objects as web services
description: Publish objects as web services to make them immediately available for your Business Central solution.
author: brentholtorf
ms.topic: how-to
ms.search.form: 810_Primary
ms.date: 01/31/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Publish a web service

Web services are a lightweight way to make application functionality available to different kinds of external systems and users. By default, [!INCLUDE[prod_short](includes/prod_short.md)] exposes several objects as web services for better integration with other Microsoft services. You can add other web services as your business requires.  

Set up a web service in [!INCLUDE[prod_short](includes/prod_short.md)], and then publish the web service so that it's available to authenticated users. All authorized users can access metadata for web services, but only users who have sufficient permissions can access actual data.  

## Creating and Publishing a Web Service

The following steps explain how to create and publish a web service.  

### To create and publish a web service  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Web Services**, and then choose the related link.  
2. On the **Web Services** page, choose **New**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!NOTE]  
    > **Codeunit** and **Page** are valid types for SOAP web services. **Page** and **Query** are valid types for OData web services. Starting with version 16.3, **Codeunit** is also a valid type for OData v4 web services, but then no URL is shown in the user interface. 
    > Also, if the database contains multiple companies, you can choose an object ID that is specific to one of the companies.  
    > Finally, the service name is visible to consumers of your web service and is the basis for identifying and distinguishing web services, so you should make the name meaningful.

3. Select the check box in the **Published** column.  

When you publish the web service, the **OData URL** and **SOAP URL** fields show the new URLs. However, for codeunits that are exposed as OData v4 unbound actions, the URL fields aren't shown.  

You can test the web service immediately by choosing the links in the **OData URL** and **SOAP URL** fields. Optionally, copy the value of the field and save it for later use. To test codeunits that are exposed as OData v4 unbound actions, follow the instructions in the [Verifying web service availability](/dynamics365/business-central/dev-itpro/developer/devenv-creating-and-interacting-with-odatav4-unbound-action#verifying-web-service-availability) section in the developer content.

> [!NOTE]
> If the objects that you expose as web services must not be accessible from [!INCLUDE[prod_short](includes/prod_short.md)] online, you must mark the methods exposed in the code as `[Scope('OnPrem')]`. For more information, see [Scope Attribute](/dynamics365/business-central/dev-itpro/developer/methods/devenv-scope-attribute).

After you publish a web service, it's available to external parties. You can verify the availability of that web service by using a browser, or choose the link in the **OData URL** and **SOAP URL** fields on the **Web Services** page. The following procedure illustrates how you can verify the availability of the web service for later use.  

### To verify the availability of a web service  

1. In your browser, enter the relevant URL. The following table illustrates the types of URLs that you can enter for different web service types.  

    > [!div class="mx-tdBreakAll"]
    > |Type|Syntax|Example|
    > |----------------|------|-------|
    > |SOAP|`https://api.businesscentral.dynamics.com/*version*/*tenant*/Production/WS/*CompanyName*/*entity*/` |`https://api.businesscentral.dynamics.com/v2.0/7acc9d3d-d354-4616-8bbd-c4fc9f2b15b3/Production/WS/CRONUS%20USA%2C%20Inc./Page/InvoiceDocument`|
    > |OData V4|`https://api.businesscentral.dynamics.com/*version*/*tenant*/Production/ODataV4/Company('*CompanyName*')/*entity*`|`https://api.businesscentral.dynamics.com/v2.0/7acc9d3d-d354-4616-8bbd-c4fc9f2b15b3/Production/ODataV4/Company('CRONUS%20USA%2C%20Inc.')/InvoiceDocument`<br/>    The company name is case-sensitive.|

2. Review the information that is displayed in the browser. Verify that you can see the name of the web service that you created.  

When you access a web service, and you want to write data back to [!INCLUDE[prod_short](includes/prod_short.md)], you must specify the company name. You can specify the company as part of the URI as shown in the examples; alternatively, specify the company as part of the query parameters. For example, the following URIs point to the same OData web service and are both valid URIs.  

```
https://api.businesscentral.dynamics.com/v1.0/OData/Company('CRONUS International Ltd.')/Customer  
```

```
https://api.businesscentral.dynamics.com/v1.0/OData/Customer?company='CRONUS International Ltd.'  
```

## Related information

[Administration](admin-setup-and-administration.md)  
[Business Central Web Services for developers](/dynamics365/business-central/dev-itpro/webservices/web-services)  
[OData request limits](/dynamics365/business-central/dev-itpro/administration/operational-limits-online#ODataServices)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
