---
title: Get the Business Central Add-in for Outlook
description: Learn how to install the Business Central add-in for Outlook for your organization or for your own use. 
author: jswymer

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, mail, Microsoft 365, Outlook
ms.search.form: 1831, 1832
ms.date: 04/27/2022
ms.author: jswymer

---
# Get the Business Central Add-in for Outlook

With [!INCLUDE[prod_short](includes/prod_short.md)], you can manage business interactions with your customers and vendors, directly in Microsoft Outlook. With the [!INCLUDE[prod_short](includes/prod_short.md)] Outlook add-in, you'll  see financial data related to customers and vendors. You can also create and send financial documents, such as quotes and invoices.  

There are two ways to get the Business Central add-in for Outlook installed, depending on your role in the organization:

- As a Microsoft 365 administrator, use *Centralized Deployment* to install the add-in automatically for the entire organization, groups, or specific users.

- As any user, install the add-in for your own use, if your admin hasn't already deployed it for you.

## About the Business Central add-in for Outlook

The Business Central add-in for Outlook consists of two smaller add-ins:

- Contact insights

    This add-in provides users with [!INCLUDE[prod_short](includes/prod_short.md)] customer or vendor information in Outlook emails and calendar appointments. It also enables you to create and send [!INCLUDE[prod_short](includes/prod_short.md)] business documents, such sales quotes and invoices to a contact. <!--To support these task, the add-in adds actions to the Outlook ribbon, in the **Business Central** group. --> 

- Document view

    When an email refers to a business document number in the email body, this add-in provides a direct, in-line link from email body to the actual business document in [!INCLUDE[prod_short](includes/prod_short.md)].

For more information about what you do with the add-ins, see [Use Business Central as your Business Inbox in Outlook](work-outlook-addin.md).

Each add-in is provided as an XML file, called a *manifest*, which must be installed in Outlook of anyone who wants this functionality. These files describe how to activate the add-ins and connect to Business Central when they're used in Outlook. Working with these files is typically done by an admin. As a normal user, in most cases, you won't have to handle with these files directly. Either your admin will set up the add-in to install automatically for you or you'll use the built-in assisted setup to handle the installation.

> [!IMPORTANT]
> Working with multiple environments? The Business Central add-in for Outlook is designed to work with a single Business Central environment. When the add-in is installed, the name of the environment is included in the add-in's manifest. This configuration means that the add-in will only connect to the environment that it was installed from. To use the add-in with a different environment, you'll open the environment and install the add-in again.

## Deploy the add-in by using Centralized Deployment as an admin

Centralized Deployment is a feature in Microsoft 365 admin center that you use to automatically install add-ins in users' Office apps, like Outlook. It's the recommended way for admins to deploy for Office add-ins to users and groups within your organization.

> [!NOTE]
> For Business Central on-premises, see [Setting Up the Add-In for Outlook Integration with Business Central On-Premises](/dynamics365/business-central/dev-itpro/administration/setting-up-office-add-ins-outlook-inbox) in the administration content (English only).

### Prerequisites

- A Microsoft 365 subscription  
- Users are assigned a Microsoft 365 license  
- Your Microsoft 365 account has the *Global Administrator* or *Exchange Administrator* role

### Deploy the add-in

1. In Business Central, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link.
2. Choose **Outlook Add-in Centralized Deployment** to start the assisted setup guide.
3. Review the first page and choose **Next** to open the page for downloading the add-ins.
4. In the **Deploy** column, select the check box for the add-ins that you want to deploy, then choose **Download and Continue**.

    A file with the name *OutlookAddins.zip* is downloaded to your device.

5. At this point, you're finished with the work you need to do in Business Central, so you can choose **Done**.

   >[!TIP]
   > Before you choose **Next**, select the **Go to Microsoft 365 (opens in a new window)** link to open and sign in to the Microsoft 365 admin center in a new browser window. You'll have to go to the Microsoft 365 admin center in a later step anyways.

6. Go the folder where the OutlookAddins.zip was downloaded, and extract the **Contact Insights.xml** and **Document View.xml** files from the .zip to a folder of your choice.

    For more information, see [Zip and Unzip files and folders](https://support.microsoft.com/en-us/windows/zip-and-unzip-files-8d28fa72-f2f9-712f-67df-f80cf89fd4e5).
7. Sign in to the Microsoft 365 admin center, then go to [Integrated Apps](https://go.microsoft.com/fwlink/?linkid=2163967).

8. Choose **Upload custom apps**.
9. On the **Upload Apps to deploy** page, choose **Upload manifest file (.xml) from device** > **Choose file**.
10. Select one of the add-files you extracted earlier, for example, **Contact Insights.xml**.
11. Follow the instructions to assign users and deploy the add-in.
12. Repeat step 9 through 11 for the other add-in file if you want.

> [!IMPORTANT]
> A green check mark appears when the add-in is deployed to the admin center. However, it can take up to 24 hours before users see the add-in in Outlook app. Users might have to restart Outlook as well.

When finished, you can always change the deployment in Microsoft 365 admin center, like assigning more users. For more information about deploying add-ins in the admin center, see [Deploy add-ins in the admin center](/microsoft-365/admin/manage/centralized-deployment-faq?view=o365-worldwide#how-do-you-target-add-in-user-assignments-with-centralized-deployment-&preserve-view=true).

## <a name="install"></a>Install the add-in for your own use

If your organization allows it, you can install the Business Central add-in for just yourself. Contact your administrator if you're not sure.

1. In Business Central, go to the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Get the Outlook Add-in**, then choose the related link.
2. Read the page and choose **Next** when ready.
3. If you want to receive a welcome email message from Business Central with overview of using the add-in, turn on **Send sample email message**.
4. Choose **Finish** to complete the installation.

Business Central will connect to your email server and install the add-in in your Outlook. This won't take long. You're now ready to start using the add-in in Outlook.

### <a name="onprem"></a>For Business Central on-premises

If you're using Business Central on-premises, installing the add-in may be slightly different.

1. In Business Central, go to the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Get the Outlook Add-in**, then choose the related link.
2. Read the page and choose **Next** when ready.
3. Do one of the following steps, depending on the page you see:

    - If you see the **Install to my Outlook** button, choose it and you're all done.
    - If you see the **Next** button, choose it. On the next page, if you want to receive a welcome email message from Business Central with overview of using the add-in, turn on **Send sample email message**. Then, choose **Finish** and you're all done.
    - If you see the **Download Add-in** button, choose it, then go to the next step.
4. When you choose **Download Add-in**, a file with the name *OutlookAddins.zip* is downloaded to your device. You should see the file at the top of the browser.

   Go the folder where the OutlookAddins.zip was downloaded, and extract the **Contact Insights.xml** and **Document View.xml** file from the .zip to a folder of your choice. For more information about how to extract files, see [Zip and Unzip files and folders](https://support.microsoft.com/en-us/windows/zip-and-unzip-files-8d28fa72-f2f9-712f-67df-f80cf89fd4e5).

5. Open Outlook, and choose **Get Add-ins** from the ribbon. Or, if you're using Outlook on the web, select the drop-down menu on any new or existing email message, then select **Get Add-ins**.
6. Choose **My add-ins** > **Add a custom add-in** > **Add from a file**.
7. Choose one of the .xml files that you extracted, like **Contact Insights.xml**, then choose **Open** > **Install**.
8. Repeat step 6 and 7 for the other .xml file, if you downloaded one.

You're now ready to start using the add-in in Outlook.

## See Also

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Getting Business Central on my Mobile Device](install-mobile-app.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Minimum Requirements for Outlook](product-requirements.md#outlook)  
[Use add-ins in Outlook on the web](https://support.office.com/article/Using-Add-ins-in-Outlook-on-the-web-8f2ce816-5df4-44a5-958c-f7f9d6dabdce?appver=OWB150)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
