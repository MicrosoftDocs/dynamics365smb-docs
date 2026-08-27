---
title: Use the Expense Agent Mobile App (preview)
description: Capture receipts on the go with the Business Central Expenses mobile app for iOS and Android, featuring document scanning and offline support.
author: brentholtorf
ms.topic: how-to
ms.date: 08/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-assisted
---

# Use the Expense Agent mobile app for iOS and Android (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The Expense Agent mobile app helps you stay productive by letting you create, review, and submit expenses directly from your iPhone or Android mobile device. The mobile app offers the same core features as the Expense Agent web app, but it's optimized for mobile use:

- **Capture receipts**: Use your phone's camera to scan receipts with live edge detection and auto-crop. The scanner captures multipage receipts if you have more than one page to scan.
- **Upload photos and files**: Choose existing photos from your gallery or upload PDF invoices stored on your device.
- **Review expenses**: Check AI-suggested details and edit them as needed.
- **Create mileage expenses**: Enter trip details and let the app calculate distance and reimbursement.
- **Submit expense reports**: Group expenses into reports and submit them for approval.
- **Work offline**: View your expenses even when you don't have an internet connection. The app refreshes data when you reconnect.

> [!TIP]
> The mobile app uses the same account and expense data as the web app. Changes you make on your phone appear on the web, and vice versa.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Get the app and sign in

The Expense Agent mobile app is available only in prerelease preview. To get the app, go to:

- [iOS](https://testflight.apple.com/join/hsJb5S1G)
- [Android](https://play.google.com/apps/testing/com.microsoft.dynamics365.businesscentral.expense)

> [!NOTE]
> For iPhone and iPad, you need iOS 17 or later. For Android, you need Android 14 or later.

After the installation is complete, open the :::image type="icon" source="../media/outlook-business-central-icon.png"::: **Expenses** app and sign in with the same credentials that you use for the Expense Management web app. The mobile app and web app share the same data. Any expense reports or expenses you create in the web app are also available in the mobile app. You stay signed in until you choose to sign out, so you don't have to enter your credentials every time you open the app.

> [!TIP]
> If you're already signed in to other Microsoft apps on your device, the app might use those credentials automatically to speed up sign-in.

<!-- [!NOTE]
> If you're designated as an approver, you also have a **Pending approval** tab, where you can review and approve expense reports submitted by others. -->

### Give the app permission to use your camera, photos, and files

The app needs access to your device camera, photo library, and files on your device to capture and upload receipts.

- On **iOS**, the app asks for permission the first time you try to scan a receipt or upload a photo. Select **Allow** when prompted. You don't need to give explicit permission for files on the device.
- On **Android**, the app asks for camera and storage permissions the first time you use these features. Select **Allow** or **While using the app** when prompted.

If you accidentally deny permission, you can change it later in your device settings:

- **iOS:** Go to **Settings** > **Apps** > :::image type="icon" source="../media/outlook-business-central-icon.png"::: **Expenses**. Turn on **Camera** and set **Photos** to **Full Access** or **Limited Access**. 
- **Android:** Go to **Settings** > **Apps** > :::image type="icon" source="../media/outlook-business-central-icon.png"::: **Expenses** > **Permissions**. Allow access to **Camera**, **Photos and videos**, and **Files** (if available).

## Create an expense

When you open the app, you start on the **Expenses** screen. The screen displays all expenses for the currently selected expense report in a scrollable feed. You can create an expense by scanning receipts, uploading files or photos, adding mileage, or sharing receipts from your phone.

Regardless of how you upload a receipt—whether by scanning, choosing from files, or sharing via your phone's Share feature—Expense Agent automatically:

- Extracts receipt information.
- Categorizes the expense.
- Itemizes receipt lines when required.
- Completes required expense fields.

### Scan receipts

Use your device's camera to scan physical receipts. The app uses your device's native scanning experience. Depending on your device and operating system, the scanner might automatically detect and capture receipts, or require you to capture them manually. Some devices also allow you to review, crop, rotate, or otherwise adjust scans before continuing.

> [!TIP]
> For best results, use good lighting and hold your phone steady. The app works with printed receipts, digital invoices, PDF files, and handwritten receipts such as taxi receipts.

You can capture one or more receipts in a single scanning session. Each receipt becomes a separate expense. Complete the following steps:

1. Select **+**, and then select **Scan receipts**.
1. Position the receipt within the camera view and capture using your device's scanning experience.
1. Scan more receipts if you have them.
1. When satisfied with the scans, confirm them in your device's camera app to return to the :::image type="icon" source="../media/outlook-business-central-icon.png"::: **Expenses** app.

Expense Agent processes the scanned receipts and creates expenses for review. Your receipts upload automatically.

> [!NOTE]
> To optimize storage usage, Expense Agent crops receipt images before processing.

### Create an expense from a file or photo

Use existing receipt files or photos stored on your device instead of capturing new images. Examples include:

- Receipts you previously photographed by using your phone camera.
- Receipts you downloaded from email or other applications.
- PDF files stored on your device.
- Image files stored on your device.

To create an expense from a file or photo:

1. Select **+**, and then select **Choose from files** or **Choose from photo library** (iPhone and iPad only).
1. Browse to and select the receipt file or photo.

After you choose the file, the Expense Agent processes the receipt and creates an expense for your review.

### Share a receipt from your camera

Use your phone's built-in **Share** option to create an expense directly from a receipt photo.

1. On your device, open a photo of a receipt.
1. Select **Share**.
1. Select :::image type="icon" source="../media/outlook-business-central-icon.png"::: **Expenses**.

The Expense Agent automatically uploads the receipt, recognizes the submitter, extracts the relevant information, creates the expense record, and processes the remaining steps.

### Add mileage

You can quickly add mileage to an expense.

1. Select **+**, and then select **Add mileage**.
1. Enter the **Starting point**.
1. Enter the **Ending point**.
1. Allow Expense Agent to calculate mileage information.

Expense Agent uses the same calculations for mileage in the mobile app and web app. Learn more at [Set up per diem and mileage allowances](expense-management-per-diem-mileage.md).

## Review and edit an expense

Review and verify an expense before you add it to an expense report.

1. Verify the expense details, and if all is well, select **Add**.
1. If needed, make a change, select **Save Changes**, and then select **Add**.

The expense is added to the expense report and becomes ready for submission.

## Delete an expense

1. Open the expense.
1. Select **Delete**.
1. Confirm the deletion.

## Move an expense to another report

You can move an expense to a different expense report in the mobile app when the expense is still in draft and the target report is editable. An editable report means it's in draft (not submitted, approved, or otherwise locked), owned by the same user, and not currently in an approval workflow. The app prevents moving expenses into reports that are submitted, approved, or locked.

1. Open the expense you want to move.

   The current expense report appears in the lower-right corner of the expense as a folder icon and the report name.
1. Select the expense report and then select the expense report you want to move to or select **New report** to create one.
1. Confirm the move. The expense is removed from the original report and added to the selected report.

Consequences and notes:

- The moved expense keeps its receipt, fields, and any reviewer comments.
- Moving an expense doesn't change the expense's status, but it can affect the totals and reimbursable amount of both reports.
- If the target report isn't editable (for example, already submitted), the app shows an error and the move fails.
- If you're offline, the move is queued and applied when the app reconnects.

## Submit an expense report

Before you submit an expense report, review all expenses and confirm that they're correct. For example, pay special attention to the following values:

- **Report Total**
- **Reimbursable Amount**

> [!IMPORTANT]
> The **Reimbursable Amount** represents the amount that the employee receives.
>
> Expenses paid by using a company credit card, corporate card, or company-funded bank account are already paid by the organization and aren't reimbursable.
>
> Employees are reimbursed only for expenses they pay themselves. Personal cash payments and personal card payments are classified as **Cash** payment methods.

To submit an expense report, follow these steps:

1. Verify all expense details.
1. Ensure the correct expense report is selected at the top of the screen.
1. Select the **Submit** button (green arrow) in the upper-right corner.

> [!NOTE]
> If you don't review and confirm some expenses, a warning message appears. Choose one of the following actions:
>
> | Action | Description |
> |----------|-------------|
> | **Cancel** | Return to the expense report and review all expenses before submission. |
> | **Move and submit** | Submit the current report and automatically move unconfirmed expenses to a new expense report. |
> 
> If you don't want to make changes, select the **Back** arrow in the upper-left corner of the screen.

## View submitted expense reports

1. Select **Submitted** at the bottom of the screen.
1. Browse the list of submitted expense reports.
1. Open a report to review its details.

## How the app works with offline mode

The app is designed for travel and intermittent connectivity. You can review expenses and view receipt images even when you're offline. For example, when you're on a flight or in an area with weak signal strength.

When you reconnect, the app automatically refreshes to pull in new expenses and upload the receipts you captured while offline. You don't need to manually sync or reopen the app.

> [!IMPORTANT]
> You can view expenses offline. The app queues receipts you capture while offline and automatically uploads them when you reconnect. Receipt processing and report submission require an internet connection and happen automatically when you're back online.

## How your data is stored

The mobile app connects to [!INCLUDE[prod_short](../includes/prod_short.md)] just like the web app. Your expense data stays in your company's [!INCLUDE [prod_short](../includes/prod_short.md)] environment.

Also like the web app, the mobile app uses AI to process receipt images. Always review the suggested details before saving an expense.

> [!NOTE]
> The mobile app doesn't store receipts permanently on your device. To protect your privacy, after you upload receipts, the app removes them from local storage.

## Troubleshooting

If you run into problems using the mobile app, try these steps:

| Issue | Solution |
|---|---|
| Can't sign in | Ensure you're using your work email address, not a personal Microsoft account. If your organization requires multifactor authentication, complete the verification steps. |
| Camera scanner doesn't open | Check that you granted the app permission to use your camera in your device settings. |
| Receipts stuck uploading | Ensure you have an active internet connection. The app queues receipts when offline and uploads them automatically when you reconnect. |
| Expense data not up to date | Pull down to refresh the **Expense reports** list. The app refreshes automatically when you reopen it, but you can manually refresh at any time. |
| App crashes or freezes | Close the app completely, then reopen it. If the problem continues, uninstall and reinstall the app. Your data stays safe in Business Central. |

If you continue to have trouble, contact your administrator or refer to [Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md).

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)  
[Upload receipts and create expenses in Expense Agent](expense-agent-upload-receipts.md)  
[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
