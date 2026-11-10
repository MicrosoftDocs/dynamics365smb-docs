---
title: Get the Business Central Add-in for Outlook
description: Learn how to download and install the Business Central add-in for Outlook for your own use, or deploy it to users and groups in your organization.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: SMTP, mail, Microsoft 365, Outlook
ms.search.form: 1831, 1832
ms.date: 11/09/2026
ai-usage: ai-assisted
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Get the Business Central add-in for Outlook

With [!INCLUDE[prod_short](includes/prod_short.md)], you can manage business interactions with your customers and vendors, directly in [!INCLUDE [outlook-name](includes/outlook-name.md)]. With the [!INCLUDE[prod_short](includes/prod_short.md)] [!INCLUDE [outlook-name-short](includes/outlook-name-short.md)] add-in, you can view financial data related to customers and vendors. You can also create and send financial documents, such as quotes and invoices.  

There are two ways to get the Business Central add-in for Outlook installed, depending on your role in the organization:

- As a Microsoft 365 administrator, use *Centralized Deployment* to install the add-in automatically for the entire organization, groups, or specific users.

- As any user, install the add-in for your own use if not already done by your admin.

## About the Business Central add-in for Outlook

The Business Central add-in for Outlook consists of two smaller add-ins:

- Contact insights

    This add-in provides users with [!INCLUDE[prod_short](includes/prod_short.md)] customer or vendor information in Outlook emails. In calendar appointments, contact lookup is limited to contacts associated with customers. It also enables you to create and send [!INCLUDE[prod_short](includes/prod_short.md)] business documents, such as sales quotes and invoices, to a contact.

- Document view

    When an email refers to a business document number in the email body, this add-in provides a direct, in-line link from email body to the actual business document in [!INCLUDE[prod_short](includes/prod_short.md)].

Learn about what you do with the add-ins in [Use Business Central as your Business Inbox in Outlook](work-outlook-addin.md).

Each add-in is provided as an XML file, called a *manifest*, which must be installed in Outlook of anyone who wants this functionality. These files describe how to activate the add-ins and connect to Business Central when they're used in Outlook. Either your admin deploys the add-ins for you, or you download the manifests from the built-in assisted setup and install them in Outlook.

> [!IMPORTANT]
> Working with multiple environments? The Business Central add-in for Outlook is designed to work with a single Business Central environment. When the add-in is installed, the name of the environment is included in the add-in's manifest. This configuration means that the add-in will only connect to the environment that it was installed from. To use the add-in with a different environment, you'll open the environment and install the add-in again.

## Deploy the add-in by using Centralized Deployment as an admin

Centralized Deployment is a feature in Microsoft 365 admin center that you use to automatically install add-ins in users' Office apps, like Outlook. It's the recommended way for admins to deploy for Office add-ins to users and groups within your organization.

> [!NOTE]
> For Business Central on-premises, learn how to set up the add-in in [Setting Up the Add-In for Outlook Integration with Business Central On-Premises](/dynamics365/business-central/dev-itpro/administration/setting-up-office-add-ins-outlook-inbox) (English only).

### Prerequisites

- A Microsoft 365 subscription  
- Users are assigned a Microsoft 365 license  
- Your Microsoft 365 account the [Exchange Administrator](/entra/identity/role-based-access-control/permissions-reference#exchange-administrator) role and meets the additional [centralized deployment admin requirements](/microsoft-365/admin/manage/centralized-deployment-of-add-ins#admin-requirements). An Exchange administrator also needs the **Application Administrator** role or app registrations enabled in Microsoft Entra ID.

### Download the add-in manifests

1. In Business Central, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Assisted Setup**, and then select the related link.
1. Select **Outlook Add-in Centralized Deployment** to start the assisted setup guide.
1. Review the first page and select **Next**. Review the privacy notice and select **Next** to open the page for downloading the add-ins.
1. In the **Deploy** column, select the check box for the add-ins that you want to deploy, then select **Download and Continue**.

    If you select both add-ins, a file named `OutlookAddins.zip` is downloaded to your device. If you select only one add-in, its XML manifest is downloaded directly.

1. At this point, you're finished with the work you need to do in Business Central, so you can select **Done**.

   >[!TIP]
   > Before you select **Done**, select the **Go to Microsoft 365 (opens in a new window)** link to open and sign in to the Microsoft 365 admin center in a new browser window.

1. If you downloaded `OutlookAddins.zip`, extract the `Contact Insights.xml` and `Document View.xml` files to a folder of your choice. The names are based on the add-in names in Business Central and can be localized.

    Learn more in [Zip and Unzip files and folders](https://support.microsoft.com/en-us/windows/zip-and-unzip-files-8d28fa72-f2f9-712f-67df-f80cf89fd4e5).

### Deploy the manifests in Microsoft 365

Use the downloaded XML files to deploy the add-ins to your users.

1. Sign in to the Microsoft 365 admin center, then go to [Integrated Apps](https://go.microsoft.com/fwlink/?linkid=2163967).

1. Select **Upload custom apps**.
1. On the **Upload Apps to deploy** page, set **App type** to **Office Add-in**.
1. Select **Upload manifest file (.xml) from device** > **Choose file**.
1. Choose one of the add-in files, `Contact Insights.xml` or `Document View.xml`, that you downloaded or extracted earlier.
1. Follow the instructions to assign users and deploy the add-in.
1. Repeat the upload and deployment process for the other add-in file if you want.

> [!IMPORTANT]
> A green check mark appears when the add-in is deployed to the admin center. However, it can take 24 to 72 hours before users see the add-in in the [!INCLUDE [outlook-name-short](includes/outlook-name-short.md)] app. Users might have to restart Outlook as well.

When finished, you can always change the deployment in Microsoft 365 admin center, like assigning more users. Learn more in [Deploy add-ins in the admin center](/microsoft-365/admin/manage/manage-deployment-of-add-ins).

## <a name="install"></a>Install the add-in for your own use

1. In Business Central, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Get the Outlook Add-in**, then select the related link.
1. Read the page and select **Next** when ready.
1. On the **Configure Outlook** page, select **Download Add-in**.
1. Find the downloaded file on your device.

   If the file is `OutlookAddins.zip`, extract the `Contact Insights.xml` and `Document View.xml` manifests to a folder of your choice. If only one add-in is available, its XML manifest is downloaded directly, and no extraction is needed. The names can be localized. Learn more in [Zip and Unzip files and folders](https://support.microsoft.com/en-us/windows/zip-and-unzip-files-8d28fa72-f2f9-712f-67df-f80cf89fd4e5).
1. In your browser, visit [https://aka.ms/olksideload](https://aka.ms/olksideload). This link opens Outlook on the web, and then loads the **Add-Ins for Outlook** dialog.
1. Select **My add-ins** > **Add a custom add-in** > **Add from File**.
1. Select one of the .xml files that you downloaded or extracted, like `Contact Insights.xml`, then select **Open** > **Install**.
1. Repeat steps 6 and 7 for the other .xml file, if you downloaded one.
1. Return to the assisted setup in Business Central. For Business Central online, select **Next**, choose whether to turn on **Send sample email message**, and select **Finish**. For Business Central on-premises, select **Finish** on the **Configure Outlook** page.

You're now ready to start using the add-in in Outlook. Learn more in [Use Business Central as your Business Inbox in Outlook](work-outlook-addin.md).

Learn more about installing add-ins in Outlook at [Use add-ins in Outlook](https://support.microsoft.com/en-us/office/use-add-ins-in-outlook-1ee261f9-49bf-4ba6-b3e2-2ba7bcab64c8).

For the current manual installation steps across Outlook clients, see [Sideload Outlook add-ins for testing](/office/dev/add-ins/outlook/sideload-outlook-add-ins-for-testing).

## Related information

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Getting Business Central on my Mobile Device](install-mobile-app.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Minimum Requirements for Outlook](product-requirements.md#outlook)  
[Use add-ins in Outlook on the web](https://support.office.com/article/Using-Add-ins-in-Outlook-on-the-web-8f2ce816-5df4-44a5-958c-f7f9d6dabdce?appver=OWB150)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
