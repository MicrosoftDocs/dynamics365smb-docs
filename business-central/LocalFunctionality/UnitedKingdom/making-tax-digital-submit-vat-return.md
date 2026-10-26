---
title: Making Tax Digital - Submitting VAT Returns
description: Business Central includes features to manage your VAT and comply with Making Tax Digital. This article describes how to set up and use these features.
author: jswymer
ms.topic: how-to
ms.search.keywords: making tax digital, VAT, HMRC
ms.search.form: 743, 10530, 10531, 10532, 10537, 10538, 10539, 
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.reviewer: jswymer
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Making Tax Digital in the United Kingdom

His Majesty's Revenue and Customs (HMRC) implemented the first steps of *Making Tax Digital*, which imposes new requirements on VAT registered businesses above the VAT threshold. [!INCLUDE [prod_short](../../includes/prod_short.md)] supports the first rounds of *Making Tax Digital*, which took effect in April 2019:

* Keeping records digitally
  Businesses must now keep all their records digitally. For users of finance systems, such as [!INCLUDE [prod_short](../../includes/prod_short.md)], this requirement is already met because they already keep their records digitally.  
* Submit VAT return electronically using [software recognized by HMRC](https://www.gov.uk/guidance/software-for-sending-income-tax-updates).  

Since 2021, the electronic statements must also include information that helps [prevent fraud](fraud-prevention-data.md).

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports Making Tax Digital and the GovTalk service.

## Making Tax Digital for VAT capabilities in Dynamics 365 Business Central

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can use the VAT Return report for creating VAT reports. The Making Tax Digital VAT features extend this capability to communicate with HMRC. For example, the Making Tax Digital VAT extension lets you:

* Retrieve VAT obligations from HMRC
* Get reminded about VAT obligations that are approaching or already past due
* Submit VAT returns to HMRC  
* View the VAT return  
* View VAT payments with HMRC  
* View VAT liabilities with HMRC  

## Set up Making Tax Digital for VAT

The *Making Tax Digital* integration uses a service connection to communicate with HMRC. [!INCLUDE[prod_short](../../includes/prod_short.md)] provides the **HMRC VAT Setup** service connection, which contains most of the information needed to communicate with HMRC. To finish the connection, give the **Dynamics 365 Business Central MTD VAT** application authority to interact with HMRC on your behalf. Microsoft manages this application on the HMRC website. In Business Central online, the authorization flow returns the authorization code automatically.
  
> [!NOTE]
> The following procedure describes the steps to set up Making Tax Digital in [!INCLUDE [prod_short](../../includes/prod_short.md)] online. If you're using [!INCLUDE [prod_short](../../includes/prod_short.md)] on-premises, refer to [Setup requirements for on-premises versions](#setup-requirements-for-on-premises-versions) before you set up the service connection.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Connections**, and then choose the related link.
1. On the **Service Connections** page, choose **HMRC VAT Setup**.
1. To open a GOV.UK website and request an authorization code, choose **Process**, then **Request Authorization Code**, and then choose **Continue**.  
1. Sign in with your HMRC credentials. To allow the **Dynamics 365 Business Central MTD VAT** application to interact with HMRC on your behalf, choose **Grant authority**.
1. Complete the authorization flow. Business Central uses the returned code to request access and refresh tokens.
1. When authorization succeeds, choose **Yes** to open **Company Information**. Verify that the **VAT Registration No.** is correct and matches the number registered with HMRC.

For on-premises installations, the authorization request opens the HMRC website instead. Copy the authorization code back to the service connection and enter it in **Enter Authorization Code**. The code is valid for 10 minutes.

On the **VAT Report Setup** page, turn on **Enabled** on the **Making Tax Digital** FastTab and accept the consent prompt. Business Central blocks MTD requests if this setting is turned off. Fill in the remaining fields as necessary. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] Learn more in [Set up VAT reporting](../../finance-setup-vat.md#set-up-vat-reporting).

> [!IMPORTANT]
> Starting in March 2022, the **User IP Address Service** must specify an endpoint for the service that your company uses to extract and submit the [IP address](fraud-prevention-data.md#ip-addresses) of the user who sends the VAT report.

### Setup requirements for on-premises versions

The app initializes an `HMRC MTD` VAT report configuration and the related VAT report setup. Check the existing configuration before creating another one. If you need to configure the reports manually, use the following values.

1. You must add a VAT report configuration on the **VAT Reports Configuration** page.  
  
    1. Create a new configuration, and choose the **VAT Return** type.
    1. Give the configuration a descriptive name, such as `HMRC MTD`.
    1. In the **Suggest Lines Codeunit ID** field, choose codeunit `745`.
    1. In the **Content Codeunit ID** field, choose codeunit `10531`.
    1. In the **Submission Codeunit ID** field, choose codeunit `10532`.
    1. In the **Validate Codeunit ID** field, choose codeunit `10533`.
    1. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

1. You must edit the VAT report setup on the **VAT Report Setup** page.  
  
    1. Expand the **Making Tax Digital** FastTab.
    1. In the **Report Version** field, choose the VAT report configuration that you created in the previous step.
    1. In the **Manual Receive Codeunit ID** field, choose codeunit `10534`.
    1. In the **Receive Submitted Return Codeunit ID** field, choose codeunit `10536`.
    1. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

1. Create an [application registration for Business Central in Azure portal](/dynamics365/business-central/dev-itpro/administration/register-app-azure). When you set up the service connection in [!INCLUDE [prod_short](../../includes/prod_short.md)], you need the following information from the registration:

    * Client ID
    * Client Secret
    * Redirect URL

The app initializes codeunit `10535` for automatic retrieval of VAT return periods and sets the update frequency to **Never**. The MTD app hides the **Auto Update Job** group on **VAT Report Setup**, so this page doesn't expose the job frequency setting.

## VAT obligations

HMRC maintains a list of VAT obligations for companies, which are the periods for which they must report VAT and the due date for the report. HMRC exposes this information through their APIs, which enables [!INCLUDE[prod_short](../../includes/prod_short.md)] to retrieve the obligations. [!INCLUDE[prod_short](../../includes/prod_short.md)] stores VAT obligations as **VAT Return Periods**, and uses them to:

* Remind you about VAT returns that are due or overdue.
* Automatically enter start and end dates when you create VAT returns.

### Retrieve the VAT return periods from HMRC

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Return Periods**, and then choose the related link.
1. On the **VAT Return Periods** page, choose the **Get VAT Return Periods** action.
1. Enter the **Start Date** and **End Date** to specify the period for which to get the VAT return periods, and then choose **OK**.  

The VAT obligations are now retrieved from HMRC and you can view them on the **VAT Return Periods** page. A confirmation page shows how many obligations were retrieved.

  > [!NOTE]  
  > Don't create VAT return periods manually when submitting VAT Returns to HMRC. VAT return periods must be retrieved from HMRC using the steps above. Creating them manually results in inability to submit VAT Returns.  

## VAT returns

Use this report to submit VAT for sales and purchase documents. For example, purchase and sales orders, invoices, and credit memos.

### Create and submit a VAT return

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Return Periods**, and then choose the related link.
1. On the **VAT Return Periods** page, choose the relevant period, and then choose the **Create VAT Return** action.
1. If you want to open the VAT return, on the confirmation page, choose **Yes**.
1. On the **VAT Return** page, to calculate and prepare the amounts for the VAT return, choose **Process**, and then choose the **Suggest Lines** action.  
1. Fill in the fields as necessary, and then choose the **OK** button. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]. VAT amounts display in the **Report Lines** section on the **VAT Return** page.  
1. To release the VAT return and prepare it for submission, choose **Process**, and then choose the **Release** action. After you release a VAT return, you can't edit it. If you need to change something, you must reopen the return. Releasing the VAT return doesn't submit it.
1. To submit the VAT return to HMRC, choose **Process** > **Submit**. Confirm the legal declaration that the information is true and complete.

After a successful submission, Business Central sets the VAT return status to **Submitted** and retrieves the submitted return from HMRC. If retrieval succeeds, Business Central changes the status to **Accepted**. If the return remains **Submitted**, retrieve the previously submitted VAT return from HMRC.

### Receive previously submitted VAT returns from HMRC

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Return Periods**, and then choose the related link.
1. On the **VAT Return Periods** page, choose the relevant VAT return period.
1. On the **VAT Return Period Card** page, choose the **Receive Submitted VAT Returns** action.

### VAT return statuses

Depending on where they are in the process, VAT returns can have one of the following statuses:

| Status | Description |
|------------|-------------------------|
| **Open** | When you create a new **VAT Return**. This status lets you run the **Suggest Lines** action. If you need to correct values, run the **Suggest Lines** action again. You can't submit a **VAT Return** with this status. |
| **Released** | Status is changed when you manually run the **Release** action. The **Errors and Warnings** FastTab is available. You can't make changes or run the **Suggest Lines** action. To make changes, you must reopen this **VAT Return**. |
| **Rejected** | If your submission wasn't successful (for example, if authentication failed), the **VAT Return** status is changed to **Rejected**. You can't reopen the **VAT Return** from this status. |
| **Submitted** | **VAT Return** is submitted using the **Submit** action or it's marked as submitted using the **Mark as Submitted** action. |
| **Accepted** | Business Central changes a **Submitted** VAT return to **Accepted** when it retrieves the submitted return from HMRC. A return can also be marked with the **Mark as Accepted** action. If the VAT return is **Accepted**, you can run the **Calculate and Post VAT Settlement** action. |
| **Partially Accepted** | Business Central can assign this status for GovTalk information collected by using the **Get VAT Returns** method. |
| **Closed** | When retrieved VAT obligations change a linked VAT return period from **Open** to **Closed**, Business Central changes an **Accepted** VAT return to **Closed**. |

## VAT liabilities and payments

If you want to check the status of your VAT, you can retrieve information from HMRC about your VAT liabilities and payments. VAT liabilities are the amounts that you owed to HMRC, and show if there are outstanding amounts to be paid. VAT payments are the actual payments your company made to HMRC.

To retrieve VAT liabilities:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Liabilities**, and then choose the related link.
1. On the **VAT Liabilities** page, choose **Process**, and then select **Get Liabilities**.
1. Enter the **Start Date** and **End Date** of the period to retrieve VAT liabilities for, and then choose **OK**.

The VAT liabilities are now retrieved from HMRC and you can view them on the **VAT Liabilities** page. A confirmation page shows how many liabilities were retrieved.

To retrieve VAT payments from HMRC:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Payments**, and then choose the related link.
1. On the **VAT Payments** page, choose **Process**, and then choose **Get Payments**.
1. Enter the **Start Date** and **End Date** of the period to retrieve VAT payments for, and then choose **OK**.

The VAT payments are now retrieved from HMRC and you can view them on the **VAT Payments** page. A confirmation page shows how many VAT payments were retrieved.

## Not in scope of this feature

This integration to HMRC and support of Making Tax Digital for VAT doesn't include support for:

* **Group VAT scenarios**

  If you submit VAT on behalf of a group of companies that share a VAT registration number (Group VAT), there isn't a built-in way to retrieve VAT entries from companies in the group. There are currently no plans to support Group VAT, and we refer to Microsoft partners to add this functionality.
* **Agent services**

  Agents can submit VAT returns on behalf of their customers, and HMRC has agent services. [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't support agent services.

## Connection errors with HMRC

If you experience "The operation has timed out" errors on an on-premises installation of [!INCLUDE[prod_short](../../includes/prod_short.md)], check any firewall settings that may be blocking the communication to and from HMRC.

## Testing the integration to HMRC in a sandbox

Due to a limitation at HMRC, it isn't possible to send test submissions of VAT Returns and test the integration in nonproduction scenarios. You can only send real VAT returns.  

Some online documentation at HMRC uses the term *Sandbox*. A sandbox is an environment that software developers, such as Microsoft and others, can use to test features during development. This environment isn't intended for customer testing, and it isn't related to [!INCLUDE[prod_short](../../includes/prod_short.md)] sandboxes.

## Related information

- [Send Fraud Prevention Data](fraud-prevention-data.md)  
- [United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
- [Set Up Calculations and Posting Methods for Value-Added Tax](../../finance-setup-vat.md)  
- [IdealPostcodes extension in the British version](ui-extensions-idealpostcodes.md)
- [The VAT Group Management Extension](../../ui-extensions-vat-group.md)  
- [Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
