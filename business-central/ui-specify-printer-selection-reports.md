---
title: Setting Up Printers
description: Learn about setting up printers that you can use for reports and documents. 
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: online printing, email printing, cloud printing, Universal Print
ms.date: 04/01/2021
ms.author: jswymer
---
# Set Up Printers

Printing documents and reports from [!INCLUDE[prod_short](includes/prod_short.md)] is an important task for business users. Users will typically want to send print jobs directly to one of your organization's printers&mdash;no matter which [!INCLUDE[prod_short](includes/prod_short.md)] client or app they're using. Because [!INCLUDE[prod_short](includes/prod_short.md)] online is a cloud service, it can't directly reach local printers connected to users' devices, but it can connect to cloud-enabled printers.

To support your print needs, [!INCLUDE[prod_short](includes/prod_short.md)] offers the following features:

|Feature|Description|Web client| Mobile app|App for Teams|
|-------|-----------|----------|-----------|--------------|
|Universal Print|Universal Print is a printer management solution available as a cloud service from Microsoft. With this feature, you can set up your printers in Universal Print, then register them for use in [!INCLUDE[prod_short](includes/prod_short.md)]. This feature requires a Universal print subscription and the **Universal Print Integration** extension|![works online](media/check.png)|![works online](media/check.png)|![works online](media/check.png)|
|Email Print|This feature lets you set up email-enabled printers. [!INCLUDE[prod_short](includes/prod_short.md)] then sends print jobs to a printer using the printer's email address. This feature requires email-enabled printers, and the **Send to Email Printer** extension.|![works online](media/check.png)|![works online](media/check.png)|![works online](media/check.png)|
|Browser printing|Print jobs are handled by the print functionality of the user's browser. If a cloud printer isn't installed and set up, or if an installed printer fails, then printing will default to the printing options for the browser. The **Printer** field on the report request page will display *(Handled by the browser)*.|![works online](media/check.png)|||

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] also supports custom printer extensions that add even more print features. So if any custom printer extensions are installed, you're application may include print features that aren't described in this article. 

## Set up Universal Print

Universal Print is a Microsoft 365 subscription-based service that runs entirely on Microsoft Azure. It gives you centralized printer management through the Universal Print portal. [!INCLUDE[prod_short](includes/prod_short.md)] makes printers set up in Universal Print available to client users through the **Universal Print Integration** extension.

![Universal Print setup](media/Universal-Print-arch.png)

The complete setup requires you work in both Microsoft Azure, using the [Azure portal](https://posrtal.azure.com), and in [!INCLUDE[prod_short](includes/prod_short.md)].

### Supported printers

[!INCLUDE[prod_short](includes/prod_short.md)] supports the same printers as Universal Print, which can be either Universal Print–compatible or non-compatible printers. Non-compatible printers can't communicate with Universal Print directly, so they require extra connector software, which is provided by Universal Print. Some older printers may not be supported. 

<!-- TODO If not installed, go to AppSource -->

### Prerequisites

**For [!INCLUDE[prod_short](includes/prod_short.md)]**

- [!INCLUDE[prod_short](includes/prod_short.md)] 2021 release wave 1 or later
- **Universal Print Integration** extension is installed

    This extension is published and installed by default as part of [!INCLUDE[prod_short](includes/prod_short.md)] online and on-premises.  You can verify whether it's installed on the **Extension Management** page. For more information, see [Installing and Uninstalling Extensions in Business Central](ui-extensions-install-uninstall.md).
- [!INCLUDE[prod_short](includes/prod_short.md)] on-premises:
  - Azure Active Directory (AD) or NavUserPassword authentication is configured
  - An application for Business Central is registered in your Azure AD tenant and [!INCLUDE[prod_short](includes/prod_short.md)]

      Like other Azure services that work with [!INCLUDE[prod_short](includes/prod_short.md)], Universal Print requires an app registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Azure Active Directory (Azure AD). The app registration provides authentication and authorization services between [!INCLUDE[prod_short](includes/prod_short.md)] and Universal Print.

      Your deployment may already be using an app registration for other Azure services, like Power BI. If so, then use the existing app registration for Universal Print as well, instead of adding a new one. The only thing you'll need to do, in this case, is modify the app registration to include the relevant print permissions for Microsoft Graph API.

      To registered an app an set the proper permissions, follow the steps described in [Register an application in Azure Active Directory](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory).

**For Universal Print**

- A Universal Print subscription/license for your organization.

    For more information, see [License Universal Print](/universal-print/fundamentals/universal-print-license).

- You have the **Printer Management** and **Global Administrator** roles in Azure.

    To manage Universal Print, your account must have **Printer Management** and **Global Administrator** roles in Azure AD. These roles are only needed for managing Universal Print. They aren't required by users to use the printers from [!INCLUDE[prod_short](includes/prod_short.md)].

### Set up Universal Print and add printers in Microsoft Azure

Before you can start managing Universal Print printers in Business Central, there are several tasks you'll need to go through to get Universal Print up and running in Azure with the printers you want use.

For detailed instructions on how to get set up, see [Get started: Set up Universal Print](https://docs.microsoft.com/universal-print/fundamentals/universal-print-getting-started) in the Universal Print documentation. Here's an overview of the steps you'll need to complete. Most of these steps are done in the Azure portal.

1. Assign Universal Print licenses to yourself and other users.

    How you assign the license depends on whether you're integrating with Business Central online or on-premises.

    - With [!INCLUDE[prod_short](includes/prod_short.md)] online, you assign licenses by using the Microsoft 365 admin center.

      For more information, see [Microsoft Admin Center Help - Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).

    - With [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you assign licenses in your Azure tenant using the Azure portal.

      For more information, see [Azure Directory - Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups).

2. Install the Universal Print connector for registering printers that can't communicate with Universal Print directly.

    Most in-market printers can't communicate with Universal Print directly. You'll have to install the Universal Print connector for these printers. For more information, see [Installing the Universal Print Connector](/universal-print/fundamentals/universal-print-connector-installation).

3. Register your printers in Universal Print.

    Registering a printer makes Universal Printer aware of the Printer.

    - For printers that can communicate directly with Universal Print, follow the steps provided by the printer manufacturer.

    - For other printers, register the printers by using the Universal Print connector. 

      For more information, see [Printer registration](/universal-print-connector-printer-registration).

4. Change printer properties (optional)

    After a printer is registered, you can view and modify printer properties, like default preferences.

    For more information, see [Manage printer metadata settings](/universal-print/fundamentals/universal-print-printer-property-settings).

5. Give users permission to the printers.

    For more information, see [Printer Permissions](/universal-print/fundamentals/universal-print-printer-permissions#printer-permissions).

6. Share the printers.

    Any printer that you want to use in [!INCLUDE[prod_short](includes/prod_short.md)] will have to be shared in Universal Print.

    For more information, see [Share a Printer](/universal-print/fundamentals/universal-print-printer-permissions#share-a-printer).

7. Enable document conversion.

    Universal Print renders content for print in XPS format. Some legacy in-market printers don't support XPS content rendering&mdash;in many cases, only PDF format. Printing to these printers will fail unless Universal Print is set up to convert documents to the printer-supported format.

    For more information, see [Document Conversion Overview](/universal-print/fundamentals/universal-print-document-conversion).

    > [!TIP]
    > If none of your printers require PDF content rendering format, we recommend that you don't enable document conversion because it might affect the print output quality.

Now, you're ready to add the printers to  [!INCLUDE[prod_short](includes/prod_short.md)], set up default printers for reports, and print.  

### Add Universal Printer printers to Business Central

After printers are set up and shared in Universal print, you're ready to them to Business Central for use. There are two ways to add Universal Print printers. You can add the printers all at once or individually, one at a time.

Adding printers individually let's you set up the same Universal Print printer in Business Central more than once. Then, for each added printer, you can change the print settings, like paper tray, size, and orientation. This way, you can set up printers for different reports and documents that have special output requirements.
  
<!-- To Do Adding printers individually lets you duplicate printers with custom , like different paper trays and paper size and orientation.  To add printers individually, you'll need to know printer's share name in Universal Print. -->

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Printer Management**, and then select the related link.
2. Select **Universal Print**, and then choose one of the following options:

    - **Add all Universal Print printers** to add all printers that aren't already added. You can use this  option even if there are already printers added. 

    - **Add a Universal Print printer** to add a specific printer.  
3. Follow the on-screen instructions.

    - If you chose **Add all Universal Print printers**, then the **Add Universal Print Printers** setup starts. <!--This setup leads you through the process of verifying your Azure AD setup (for on-premises), checking your Universal Print license, and then finally adding the printers.-->

    - If you chose to **Add a Universal Print printer**, then the **Universal Printer Settings** page appears. Fill in the **Name** field, the select **...** next to the **Print Share in Universal Print** field to select the Universal Print printer. Fill in the remaining fields as needed. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
  
    These actions verify your Azure AD setup (for on-premises), check that your have Universal Print license, and then finally adding the printers.

    > [!NOTE]
    > For on-premises, if this is the first time connecting to Universal Print, the AZURE ACTIVE DIRECTORY SERVICE PERMISSIONS page appears and you'll be prompted to give consent to Azure Services. You only have to do give consent once.

After a printer has been added, you can view and change its settings from the **Printer Management**. Just select the printer, then choose **Edit printer settings**. 

<!--
### Troubleshooting

#### You don't see the a printer in the 

The printer is not shared in Universal Print.

### You get an error when tryong to add all or a single printer

You have'nt been assigned a Uincersla Print license.

There was an error fetching printers shared to you. You don't have access to the data. Make sure your account has been assigned a Universal Print license and you have the required permissions.
or 
You don't seem to have access to Universal Print. Make sure you have a Universal Print subscription, and that your account has been assigned a Universal Print license.

## Could not upload the document to print job 50.

There is a technical problem withe the printer. Unsupported document-format: application/pdf. Supported formats: Attribute document-format-supported: SimpleIppValue-Type:MimeMediaType-Value:application/oxps

## You don't have access to the printer

- You have not been assigned a Up license
- You have not been given access to the printer in UP.
- (On-prem) The app registration has been broken
-->
## Set up Email Print

### Prerequisites

- [!INCLUDE[prod_short](includes/prod_short.md)] 2020 release wave 1 or later
- **Send to Email Printer** extension is installed

    This extension is installed by default. For information about installing extensions, see 
- Email functionality is set up.

   For more information, see [Set Up Email](admin-how-setup-email.md).

### Add an email printer

The **Printer Management** page shows you the printers that are currently set up. The page also gives you access the **Settings** page for each printer to edit an existing setup or set up a new printer.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Printer Management**, and then select the related link.
2. Select **Email Print**, and then choose **Add an email printer**.
3. On the **Email Printer Settings** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > You must manually select the appropriate paper size for a printer as no local printer or user settings can be stored.
    >
    > Beware that the Email Printer extension is set to **A4** paper size by default, which isn't suited in North America, for example.

### Privacy Notice

If you use the Email Printer extension, then all or some print jobs will be sent to the email address configured for the printer. We strongly recommend that a unique email ID is tied to a printer device using only the official services provided by the hardware manufacturer, such as HP ePrint, KonicaMinolta EveryonePrint, or Epson Email Print.

Take all necessary privacy precautions, including ensuring that the email printing solution has properly configured permissions, privacy settings, and retention policies. It is your responsibility to provide a correct, verified, and operational email address. For more information, see [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).


## <a name="default"></a>Set up default printers

There are a couple ways to set up printers that will be used by default for print jobs. A default printer is useful if you work with different reports that require different printers because of their placement in the company or their output capabilities.

### Set a printer as a default printer for all print jobs

The **Printer Management** page lets you set up a printer as a default printer for all print jobs. You can specify the printer as default for you only or for all users.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Printer Management**, and then select the related link.

    > [!TIP]
    > You can also open the **Printer Management** page from the **Printer Selections** page by choosing **Printer Management**.  
2. On the **Printer Management** page, select a printer from the list, choose **Manage**, then choose **Set as my default printer** or **Set as default printer for all users**.

> [!NOTE]
> Setting a default printer from the **Printer Management** will add an entry in the **Printer Selections**.

### Set a default printer for specific reports

The **Printer Selections** page let's you specify the printer that a report will use by default. Default printers are set on a user-account basis. You can set a default printer for just yourself, another user, or all users.

> [!IMPORTANT]
> For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, the **Printer Selections** page can only be used for cloud printers defined by printer extensions, like Email Print and Universal Print printers. It can't be used for local printers.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Printer Selections**, and then select the related link. Instead, from the **Printer Management** page, select a printer, and then choose the **Printer Selections** action.
2. Choose the **New** action to add a printer selection for a specific report.
3. Fill in the fields as necessary.

The specified report is now set up to print to the selected printer by default.

> [!NOTE]
> When you print the report in question, you can select a different using the **Print** field on the request page.

> [!NOTE]
> If you do not set a report up for a specific printer on the **Printer Selections** page, then it will be printed to the default printer of the company, as defined from the **Printer Management** page.

You or the administrator can also use the **Printer Selections** page to define other variations of printing for users and reports. The following table describes the combination of values to specify different printing setup for a report.

|To                                                 |Set the following values                                             |
|---------------------------------------------------|---------------------------------------------------------------------|
|Print a report to a specific printer for all users |Specify values in the **Report ID** and **Printer Name** fields and leave the **User ID** field blank.|
|Print all reports to a specific printer for a specific user|Specify values in the **User ID** and **Printer Name** fields and leave the **Report ID** field blank. This entry does the same as the **Set as my default printer** action on the **Print Management** page.|
|Set the default printer for all reports for all users|Specify a value in the **Printer Name** field and leave the **User ID** and **Report ID** fields blank. This entry does the same as the **Set as default printer for all users** action on the **Print Management** page.|
|Print a specific report to the user's default printer|Specify a value in the **Report ID** field and leave the **Printer Name** and **User ID** fields blank.|
|Print a specific report to a specific printer for a specific user|Specify values in all three fields.|

> [!NOTE]
> More specific printer selections take precedence over a more general printer selections. For example, a printer selection that has values in the **User ID**, **Report ID**, and **Printer Name** fields takes precedence over a printer selection that has blank entries in the **User ID** or **Report ID** fields.

### Sizing Print Jobs

Cloud printing is designed for documents of a reasonable size. Most cloud services, including PrintNode and HP ePrint, have a limit of 10 MB per job. If you need to print larger reports, you may have to split them in multiple printouts.

## See Also

[Printing a Report](ui-work-report.md#PrintReport)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Run Batch Jobs](ui-how-run-batch-jobs.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]