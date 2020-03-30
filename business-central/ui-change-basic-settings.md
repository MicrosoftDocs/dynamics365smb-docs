---
title: Viewing and Editing Basic Settings | Microsoft Docs
description: Learn how to change some basic settings, for example, the Role Center, company, or the work date.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: change Role Center, notification, change company, change work date
ms.date: 04/01/2020
ms.author: sgroespe

---
# Change Basic Settings

On the **My Settings** page, you can see and change basic settings for [!INCLUDE[d365fin](includes/d365fin_md.md)]. The changes that you make will only affect your workspace, not the workspaces of other users.  

## <a name="role-center"></a> Role Center
The Role Center represents the home page, a starting screen that is designed for the needs of a specific role in an organization. Depending on your role, the Role Center gives you an overview of the business, your department, or your personal tasks. It also helps you navigate to your daily tasks and find work that is assigned to you.

-   At the top, the navigation allows you to switch between customers, vendors, items, and other important lists of information. Similarly, actions allow you to initiate tasks, such as create a new sales invoice, directly from the Role Center.

-   In the center, you find the **Activities** area, which shows current data and can be clicked or tapped to view more detailed information. Key performance indicators (KPIs) can be set up to display a selected chart for a visual representation of, for example, cash flow or income and expenses. You can also build up a list of favorite customers on the Role Center for business accounts that you do business with often or need to pay special attention to.

### To change the role
The default role is **Business Manager**, but you can select another role to use a role center that fits your needs better.
1. In the top right corner, choose the **Settings** icon ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then choose the **My Settings** action.
2. On the **My Settings** page, in the **Role** field, select the role that you want to use by default. For example, select **Accountant**.
3. Choose the **OK** button.

## <a name="company"></a>Company
A company functions as a container for data in [!INCLUDE[d365fin](includes/d365fin_md.md)]. There can be multiple companies in a database, but only one can be selected at a time.

The default company is called CRONUS and contains demonstration data only. You can create a new company with custom data. For more information, see [Creating New Companies](about-new-company.md).

## To change the company name
The company name is always displayed at the top left corner and works as an action that you can choose to go back to the Role Center. You can change this name on the **Company Information** page.

1. Choose the ![Sprocket icon to open the Settings menu](media/ui-experience/settings_icon_small.png) icon, and then choose the **Company Information** action.
2. In the **Name** field, enter the new company name.
3. Leave the page. The system restarts and displays the new company in the top left corner.

## To display a company badge for quick access to company information  
You can add a customized badge in the top right corner, which you can choose to quickly view company name and tenant information in a pop-up box.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.
2. On the **Company Badge** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

> [!NOTE]
> If a company badge is defined, then you cannot change the company name as described in [To change the company name](ui-change-basic-settings.md#to-change-the-company-name)

## <a name="work-date"></a>Work Date
The most commonly used work date is today's date. You may have to temporarily change the work date to be able to perform tasks, such as completing transactions for a date that is not today's date.

> [!TIP]  
> In all date fields, type **t** to quickly enter today's date, and type **w** to quickly enter the work date, which is the value in the **Work Date** field on the **My Settings** page.

> [!IMPORTANT]  
>  After you change the work date, if you sign out or switch to another company, the work data reverts to the default work date. So the next time you sign in or switch back to the original company, you may have to set the work date again.

### Work Date Indication
Whenever the work date is not set to today's date, then two types of indicators will appear on pages that can be edited and where the work date is therefore critical:

- A reminder appears at the top of the page that tells you what the work date is set to. The reminder provides a direct link to the work date setting on the **My Settings** page so you change the date if you want. From the reminder, you can also choose to dismiss the reminder for the rest of your session. Unless you change the work date to "today", the reminder will appear the next time you sign in.

- If you dismiss the reminder, the work date will appear in the title of the page.  
-->
If the work date is not set to the current day (today), then on all pages where you can edit data, the current work date is shown in the upper-left corner of the page.

## <a name="region"></a> Region

The **Region** setting determines how dates, times, numbers, and currencies are shown or formatted.

## <a name="language"></a> Language
Changes the display language. This field appears only when there is more than one language to choose from.

The initial language is either determined by the administrator or by your browser settings when you sign up for [!INCLUDE[d365fin](includes/d365fin_md.md)]. The language that you set will be used on all devices that you sign in from, such as a phone or tablet.

Additional languages for [!INCLUDE[prodshort](includes/prodshort.md)] can be installed from AppSource. While all supported display languages are shown in the list, the administrator must install the releant language app to the tenant before users can switch to the new language in [!INCLUDE[prodshort](includes/prodshort.md)].  

## Changing When I Receive Notifications
Choose this link to view or change the notifications that you get about certain events or changes in status, such as when you are about to invoice a customer who has an overdue balance, or the available inventory is lower than the quantity you are about to sell. For more information, see [Managing Notifications](ui-smart-notifications.md).

## See Related Training at [Microsoft Learn](/learn/modules/personalize-ui-dynamics-365-business-central/index)

## See Also
[Creating New Companies](about-new-company.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
