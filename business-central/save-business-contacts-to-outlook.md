---
title: Save Business Contacts to Microsoft Outlook
description: Learn how to synchronize Business Central contacts with Microsoft Outlook and Teams to streamline communication and access contact details effortlessly.
author: mikebc
ms.author: mikebc
ms.reviewer: jswymer
ms.topic: how-to
ms.collection: get-started #Required; If this isn't a getting started article, don't remove the attribute, but leave the value blank. The values for this attribute will be updated over time.
ms.date: 03/13/2026
ms.custom: bap-template #Required; don't change.
---

# Save business contacts to Microsoft Outlook

If you use Outlook or Teams to contact and collaborate with people outside your organization, you often need their contact details, like email address and phone number, that are stored in Business Central. The **Contacts** list in Business Central typically contains the people or organizations you do business with, such as customers, vendors, banks, or even leads for new business, connecting them to your organization's business processes.

To help you stay in the flow of work and avoid switching from Outlook or Teams, Business Central offers a synchronization feature that saves your business contacts to Outlook and Teams. You can then easily access them just like any other contacts. When you synchronize contacts, the are saved to your Microsoft 365 contacts list and show up in the People page in Outlook and Teams. From there, they're only visible to you. You can then search for a specific contact from the To field of a draft email, set up group chats, call, or schedule meetings.

## Quick start

To save business contacts to Outlook, sign in to Business Central, find and go to the **Contacts** list, select the **Synchronize with Outlook...** action, and follow the guided instructions. Do this task periodically to get the latest business contacts into your Outlook.

## Prerequisites

- Your work account has a license to use Business Central and Microsoft 365.
- You have access to Microsoft Outlook or Microsoft Teams on your desktop, browser, or mobile device.
- You have access to Contacts in Business Central.

## How to save Business Central contacts to Outlook and Teams

The following steps guide you through copying contacts stored in Business Central and saving them to your contacts list stored in Microsoft 365, so that they're accessible in both Outlook and Teams. 

1. In Business Central, use Alt+Q or select the search icon in the top bar to search for the Contacts page.
1. Go to the Contacts list page.
1. In the action bar, expand More options, then select **Actions** and **Synchronize with Outlook...**.
1. Select **Next**. 
1. Configure which contacts to synchronize:

   1. Use the **Choose contacts** option to filter your Business Central contacts list to only those contacts you want to save to Outlook. For example you can filter your contacts list by salesperson code, city, country/region, or most other fields on contact records in Business Central.
   1. Use the Contacts folder option to select where your business contacts are stored and organized in the **People** page in Outlook. 
   1. The first time you synchronize with the selected folder, Business Central suggests a full synchronization.
   1. Select **Next** for Business Central to search for contacts that match your filters and folder you specified in the previous step. This operation can take a few minutes if you have many contacts.

1. Preview the contacts that will be synchronized:

   1. Select the first link to preview the contacts found in Business Central that match your filter criteria and aren't yet saved to Outlook. From the preview, you can also choose to exclude specific contacts using the **Exclude**, **Exclude selected**, or **Exclude All** actions. 
   1. Select the second link to preview the contacts found in the Outlook contacts folder you specified earlier that don't exist in Business Central. This information helps you understand how your business contacts will now be saved alongside all your other contacts. 
   1. By default, Business Central synchronizes by saving contacts to Outlook with no change to Business Central data. You shouldn't change the setting to update both Business Central and Outlook, until you understand the risks. Learn more about two-way synchronization in [Updating Business Central by saving contacts from Outlook and Teams](#updating-business-central-by-saving-contacts-from-outlook-and-teams).

1. Select **Synchronize** to begin copying contacts. This step can take a few minutes if you have many contacts.
When synchronization is complete, Business Central displays a summary of activity, such as how long it took, the number of contacts processed, and any errors that occurred during synchronization. Contacts are now ready to access in Outlook.
1. Select Close to end the task and close the page.

## Tips and tricks

- Understanding conditions for synchronizing a contact

  - Only contacts of type Person are saved to Outlook and Teams. Contacts of type Company are always ignored during synchronization.
  - Contacts that don't have an email address are always ignored.
  - If a contact with the same email address is found in Outlook, it's assumed to be the same contact and isn't copied again or overwritten in Outlook.  
  - If you changed the email address of a contact in Business Central, it will be considered a new contact and created as a duplicate contact in Outlook the next time you synchronize.
  - If the contact is already saved to Outlook and you modified any other fields for that contact in Business Central, those changed fields aren't saved to Outlook the next time you synchronize.
  - If you deleted a contact in Outlook, but kept it in Business Central, the contact is recreated in Outlook the next time you synchronize.

- Choosing which contacts to synchronize

  You can choose which contacts to synchronize from the **Choose contacts** option in the Synchronize contacts page. For example you can filter your contacts list by salesperson code, city, country/region, or most other fields from contact records in Business Central. Filtering the contacts list page directly has no effect on which contacts are synchronized.

- Keeping your business contacts separate from other contacts in Outlook and Teams

  The **People** page in Outlook and Teams offers different ways to organize your contacts. Depending on the version of Outlook and Teams you use, contacts might be organized into separate contact lists, folders, or categories. When synchronizing contacts, select the "Default" folder if you want your business contacts to be saved to the root, default set of contacts in Outlook and Teams. This folder most likely already contains contacts you saved while working in Outlook and Teams, and is the simplest way of managing all of your contacts. To keep the list of contacts originating from Business Central separate from all your other contacts, you should use a specific folder instead.

- Working with multiple companies

  Business Central allows setting up and using multiple companies within your organization. When you save contacts to Outlook, only contacts from the company you're currently signed into in Business Central are copied. If you work with contacts registered in different companies, you need to switch company and synchronize again. If you want to organize contacts by company in Outlook, you must first create a folder per company in Outlook. Then, ensure you select the correct folder that matches the company you're signed into when synchronizing from Business Central.

- Working with large contact lists

  When the volume of contacts to be synchronized is large, you should plan for a few minutes of waiting time until synchronization completes. Business Central typically takes around 3 minutes to synchronize 1,000 contacts.

- Synchronization and security

  - When Business Central synchronizes contacts, it doesn't grant those contacts any new access or permissions to Business Central or any resources within your organization. Synchronization isn't a security feature, and copying contacts to Microsoft 365 doesn't share your emails, chat, or calendar with anyone else.
  - When you save contacts to Microsoft 365, those contacts are stored in your own list of contacts attached to your work account: no other users can open their Outlook or Teams and see those contacts, unless they also use the synchronization feature. 
  - When you save contacts from Microsoft 365 to Business Central, any contacts you saved are visible to others within your organization. Learn more about how saving works in [Updating Business Central by saving contacts from Outlook and Teams ](#updating-business-central-by-saving-contacts-from-outlook-and-teams).
- Using Business Central as an external user

  If you have access to Business Central, Outlook or Teams as a guest user, external member, or B2B Direct user within that organization, synchronization isn't supported.
- Exchange Server
  
  Contact synchronization uses the Microsoft Graph technology for efficient and secure handling of contacts. If your organization uses Exchange Server instead of Exchange Online, synchronization isn't supported.
- Business Central on premises

  Synchronizing contacts is also possible when signing into Business Central on premises, as long as your organization uses Exchange Online. Synchronization can take longer in this scenario.
- Synchronization with older version of Business Central

  In Business Central versions earlier than version 28, contact synchronization worked differently. From version 28 onwards, background synchronization jobs are no longer possible. Each user must independently synchronize to their own Microsoft 365 account, and it isn't possible to merge contact information when a similar contact in Business Central and Outlook is found.
- Troubleshooting synchronization issues

  Because contacts change over time in both Business Central and Outlook or Teams, contact information and duplicate contacts can sometimes become problematic for synchronization. You can enable the Force full sync option from the synchronization page to ignore the last time your contacts were synched, and force a resynchronization of contacts. 

## Updating Business Central by saving contacts from Outlook and Teams

The synchronization feature also allows more advanced two-way synchronization between Business Central and your contacts stored in Microsoft 365. If you only update Outlook, no changes are made to the contact list in Business Central. If you set the **What to update** option to "Business Central and Outlook" in the synchronization page, the contacts from the specified folder in Outlook and teams are also copied back to Business Central and other users might be able to see them.

Choosing this option isn't recommended. Only choose it if you know which nonbusiness contacts are stored in the folder you selected and are ready to share them with the rest of your organization. For example, you risk copying personal contacts, internal contacts, or other external contacts to Business Central. Microsoft might remove this two-way synchronization in the future.

## Related information

<!--Remove all the comments in this template before you sign-off or merge to the main branch.-->
