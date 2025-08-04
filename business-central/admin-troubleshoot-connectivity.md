---
title: Troubleshoot connectivity
description: Describes how to use the Troubleshoot Connectivity page to identify and fix problems connecting to Business Central online.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: connectivity, troubleshooting, connection problems
ms.date: 01/09/2024
ms.author: jswymer
ROBOTS: NOINDEX
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Troubleshoot connectivity for Business Central

> **APPLIES TO:** [!INCLUDE[prod_short](includes/prod_short.md)] Online
>
> This feature is currently in preview. The functionality and documentation may change in later releases. If you would like to contribute to the documentation based on your own findings, please select ![Edit article in GitHub.](media/github-edit-pencil.png) **Edit**, and propose changes. Then we'll take a look!

[!INCLUDE[prod_short](includes/prod_short.md)] Online includes the **Troubleshooting Connectivity** page that you can use to identify problems with your connection to the online service. There are several things that affect connectivity to Business Central, like the firewall settings of your network or domain name service configuration. The page lets you run a list of checks that diagnose common Business Central connectivity issues. You can use the information to try to fix the problems yourself, or pass it on to your support representative.

> [!NOTE]
> The **Troubleshooting Connectivity** page doesn't test network performance or reliability, like the speed of your connection. It only verifies connectivity to different resources.

## Start the connectivity check 

1. Open an Internet browser.
2. In the address, enter the URL that you use to open Business Central and add `/connectivity` at the end. 

    For example, if you use `https://businesscentral.dynamics.com`, then enter:

    ```http
    https://businesscentral.dynamics.com/connectivity
    ```

    Or, if the URL includes the tenant ID, like `https://businesscentral.dynamics.com/aaaabbbb-0000-cccc-1111-dddd2222eeee`, then you'd enter:

    ```http
    https://businesscentral.dynamics.com/aaaabbbb-0000-cccc-1111-dddd2222eeee/connectivity
    ```
 
3. On the **Troubleshooting Connectivity** page, choose **Start check**.

    A series of checks is run, and the result of each check is shown:

    - ![Connectivity check succeeded.](media/connectivity-check.png) indicates the check succeeded.
    - ![Connectivity check failed.](media/connectivity-failed.png) indicates the check failed. Review the message below the check for more details.
    - ![Connectivity check was not run.](media/connectivity-blocked.png) indicates the check wasn't run, typically because of a failure of a previous check. Review the message below the check for more details.

4. To run the check again, choose **Restart check**.

The following sections explain the checks that are run, and provide some tips for fixing any problems.

## Basic internet connectivity

Checks that you have connection to the Internet by verifying that you can access a known public domain, like www.bing.com.

|Problem|Things to try|
|-------|-------------|
|Your browser doesn't support this check|Open the page in a supported browser, and try again. For a list of supported browsers, see [Minimum Requirements for Using Business Central - Browsers](product-requirements.md#browsers)|
|Failed to ping the server at the following URL: {url}|Check Firewall settings.|

## CDN (content delivery network) resources loading

[!INCLUDE[prod_short](includes/prod_short.md)] uses Azure Content Delivery Network (CDN) to provide resources that are required to run the Business Central Web client. This check verifies that the required resources are available and accessible by pinging the Business Central instance in CDN.

|Problem|Things to try|
|-------|-------------|
|Your browser doesn't support this check|See **Basic Internet connectivity** check.|
|Failed to ping the server at the following URL: {url}|Check Firewall settings.|

## User authentication

Checks that the current user signs in with a valid Business Central account.

|Problem|Things to try|
|-------|-------------|
|No user is currently authenticated|Sign in to Business Central with valid user name and password.|

## Business Central environments discovery

Checks for Business Central environments that are available to an authenticated user, then verifies whether the user can be authenticated in the environment.
<!-- example: Your user name or password is incorrect, or you do not have a valid account.. Request duration: 332 milliseconds)-->

|Problem|Things to try|
|-------|-------------|
|No authenticated user to perform this check for|See the **User authentication** check.|
|Failed to retrieve available environments for your account.|Check the list of available environments in the Business Central admin center.|
|Your user name or password is incorrect, or you don't have a valid account.| Verify that you sign in using the correct user name and password.|

## Application service connectivity

Checks that the authenticated user can connect to a discovered environment, typically starting with the production environment.

|Problem|Things to try|
|-------|-------------|
|No authenticated user to perform this check for|See the **User authentication check**.|
|Failed to retrieve available environments for your account.|See **Business Central environments discovery**.|
|No cluster address to perform this check for|Check the list of available environments in the Business Central admin center.|
|Version endpoint doesn't exist|Check the list of available environments in the Business Central admin center.|

## Web server connectivity

Checks that the authenticated user can successfully establish connections with the web server.

|Problem|Things to try|
|-------|-------------|
|No authenticated user to perform this check for|See the **User authentication check**.|
|Failed to retrieve available environments for your account.|See **Business Central environments discovery**.|
|No cluster address to perform this check for|Check the list of available environments in the Business Central admin center.|
|Failed to establish a connection with the web server|Clear the cache and reload the page.|

## Service health status

Reports Business Central's service health status by checking for declared outages.

|Problem|Things to try|
|-------|-------------|
|No authenticated user to perform this check for|See the **User authentication check**.|
|Sorry, Business Central is temporarily unavailable. Try again later.|Try again later.|

## Related information

[Resources for Help and Support](product-help-and-support.md)  
[Overview of Tasks to Set Up Business Central](setup.md)  
[Frequently Asked Questions about Using Business Central](across-faq.yml)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[The Business Central Admin Center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center)

[!INCLUDE[footer-include](includes/footer-banner.md)]
