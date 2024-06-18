---
title: Get SmartList Designer
description: Install the SmartList Designer so that you can create queries across your Business Central data.
author: brentholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: SmartList
ms.date: 10/01/2020
ms.author: bholtorf
ROBOTS: NOINDEX, NOFOLLOW
---
<!--# Get SmartList Designer

The following procedure will take you through the steps to install and set up SmartList Designer with your Business Central tenant. SmartList Designer must be installed and configured to your Business Central tenant before SmartList queries can be created.

> [!NOTE]
> SmartList Designer must be installed once in the [!INCLUDE [prodshort](includes/prodshort.md)] online tenant and can then be used by any user who has the relevant permissions.

## To install SmartList Designer

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SmartList Designer Setup**, and then choose the related link.
2. Choose the **Install SmartList Designer from AppSource** link.
3. Choose the **GET IT NOW** button.
4. If prompted, enter your account name and password.
5. Read the disclaimer, and choose **Continue** if you agree. If you do not agree, close the message by select the X in the upper right corner of the message.
6. Specify the environment that you want to install SmartList Designer into.
7. Choose the relevant fields to agree to each of the terms that are listed.
8. Choose **Install**.
9. Navigate back to the **SmartList Designer Setup** page in [!INCLUDE [prodshort](includes/prodshort.md)].
10. Verify that the **SmartList Designer App ID** and **Microsoft Entra tenant ID** fields are populated.
11. Select **OK**

> [!Note]
> It can take several minutes for the SmartList Designer app to be recognized.

> [!Tip]
> If the **SmartList Designer App ID** field remains blank after several minutes, navigate to [PowerApps.microsoft.com](https://powerapps.microsoft.com/), log in with your administrative account, choose the environment that you installed SmartList Designer in, choose the context menu next to the SmartList Designer app, and copy the app ID. You can then paste the value into the **SmartList Designer App ID** field in [!INCLUDE [prodshort](includes/prodshort.md)].

## <a name="permissions"></a>SmartLists and permissions

By default, only users that have SUPER permissions can create and preview SmartList queries. You can grant permission to other users to create and preview SmartList queries by assigning them the *SmartList Designer* permission set, or adding users or user groups to the *SmartList Designer* permission set. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

<!--Permissions to create and preview SmartList queries are two separate permissions. To create a SmartList query, the user must have permissions to system object 9600. To preview a SmartList query, the user must have permissions to system object 9500.-->

<!--### Permission to preview SmartLists

Permissions will need to be granted to any user that should have the ability to preview the results of a SmartList query definition. To grant this permission, navigate to permission sets, select the SmartList Designer permission set, and add permissions to system object 9605.  

> [!IMPORTANT]
> By granting this permission, you are granting the user the right to preview any data results from the SmartList query being defined. The user must still have permissions to the tables defined in the query in order to see data.

### SmartList query permissions

Users will need to be granted permissions to each SmartList query created for them to view the SmartList query. To do this, navigate to permission sets, create a new permission set, add permissions to the permission set and then add users or user groups to the permission set.  

To add permissions to the user defined permission set, select **Permissions** once the user-defined permission set is created. From the **Permissions** page, select **SmartList Permissions** from the actions at the top. The action may be hidden under the (…) option.  

Add the desired SmartList queries to the user-defined permission set. Permissions can also be added from the **SmartList Management** page however, the user-defined permission set must exist to use that functionality.  

## See also

[Create Custom Queries using SmartLists](bi-smartlists.md)  -->
