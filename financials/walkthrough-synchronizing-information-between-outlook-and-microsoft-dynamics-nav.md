---
    title: Walkthrough - Synchronizing Information Between Outlook and Microsoft Dynamics NAV | Microsoft Docs
    description: You can set up synchronization between [!INCLUDE[d365fin](includes/d365fin_md.md)].
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Walkthrough: Synchronizing Information Between Outlook and Microsoft Dynamics NAV
You can set up synchronization between [!INCLUDE[d365fin](includes/d365fin_md.md)].  

 The synchronization framework provides default mapping between the [!INCLUDE[d365fin](includes/d365fin_md.md)] contacts, salesperson, and to-dos, and Microsoft Outlook contacts, tasks, and meetings. You can synchronize the entities either manually or automatically at set intervals.  

> [!IMPORTANT]  
>  You can create new a salesperson contact in Outlook, but that contact will not be synchronized to [!INCLUDE[d365fin](includes/d365fin_md.md)] as a salesperson.  

 One of the strengths of the [!INCLUDE[d365fin](includes/d365fin_md.md)] Outlook synchronization feature is that it can be customized without adding code. It is fairly simple to add more fields in order to optimize synchronization.  

 The default setup contains mapping for five different [!INCLUDE[d365fin](includes/d365fin_md.md)] entities:  

-   To-dos of type Meeting  

-   Contacts of type Company type  

-   Contacts of type  Person type  

-   Salespeople  

-   To-dos of type blank or Phone  

 Companies might want to add more fields to this mapping. For more information, see the "Customizing Synchronization Fields" section in this walkthrough.  

## About This Walkthrough  
 This walkthrough illustrates the following tasks:  

-   Creating a to-do, and synchronizing it with Outlook.  

-   Handling a conflict between different data on the same record.  

-   Customizing fields that are being synchronized.  

> [!NOTE]  
>  A conflict will only appear if changes have been made in both applications after the last synchronization. Therefore, some steps in this walkthrough force a conflict so that you can practice solving it. In this case, you enter two different telephone numbers for the same contact, and then handle the conflict.  

## Roles  
 This walkthrough demonstrates tasks that are performed by the following user roles:  

-   Account Manager, Michael  

-   Sales Representative, David  

> [!NOTE]  
>  So that you can quickly begin performing the following procedures, you will use your own ADD INCLUDE<!--[!INCLUDE[navnow](includes/demoname_md.md)]--> database. See the "Prerequisites" section that follows for information about the required Outlook integration setup.  

## Prerequisites  
 To complete this walkthrough, you will need:  

-   Perform the steps in the walkthrough: [Walkthrough: Setting Up Outlook Synchronization](Walkthrough:%20Setting%20Up%20Outlook%20Synchronization.md).  

-   Ensure that web services are running.  

-   In [!INCLUDE[d365fin](includes/d365fin_md.md)], make sure that the following is true:  

    -   Outlook Integration is installed.  

    -   [!INCLUDE[d365fin](includes/d365fin_md.md)] is installed.  

    -   Your name is added as a salesperson, with your name and email address defined exactly as they are in your Outlook profile.  

    -   Your name is assigned as a user to synchronization entities.  

-   In Outlook, make sure that the following is true:  

    -   [!INCLUDE[d365fin](includes/d365fin_md.md)] Synchronization buttons are displayed in the Add-ins tab on the Outlook ribbon.  

    -   The connection between [!INCLUDE[d365fin](includes/d365fin_md.md)] and Outlook is working. To test the connection, choose the **Settings** button, and then on the **Connection** tab, choose **Test Connection**.  

## Story  
 Michael is an account manager for CRONUS International Ltd. He works primarily in the CRONUS office, and uses [!INCLUDE[d365fin](includes/d365fin_md.md)]. His coworker, David, is a sales representative who works mainly in the field and uses Outlook to track contacts, tasks, and appointments. Because Michael and David share information, they synchronize their information regularly throughout the day. This enables Michael to set appointments for David, while also keeping track of David's activities in the field.  

 In this scenario, Michael creates an appointment for David to meet with an existing customer. When David synchronizes, he sees the meeting that Michael has created. He does not think that he can drive to the location in time, so that he moves the meeting to another day in his Outlook calendar. He synchronizes again and the changes are updated in [!INCLUDE[d365fin](includes/d365fin_md.md)], so that Michael can track the change.  

 Michael attempts to call the contact, but the telephone number is incorrect because someone else has entered a new number in Outlook and not yet synchronized with [!INCLUDE[d365fin](includes/d365fin_md.md)]. Michael reviews the conflict details, determines that the problem is related to the telephone number, and resolves the conflict.  

 Michael also realizes that he has to add some additional fields to the entities that are synchronized. He adds the territory code fields as user-defined fields to the company contact information so that they will be displayed in both Outlook and [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## Performing a Synchronization  
 First, Michael sets an appointment for David to meet with a customer by creating a to-do in [!INCLUDE[d365fin](includes/d365fin_md.md)], and then synchronizing with Outlook, so that the appointment is displayed on the team calendar.  

#### To create a to-do and synchronize it with Outlook  

1.  In the **Search** box, enter **Contacts**, and then choose the related link.  

2.  In the **Contacts** list, select the contact card for **A. Gibson's Law Firm**, **CT100006**, and on the **Home** tab, in the **Manage** group, choose **Edit**.  

3.  On the contact card, on the **General** FastTab, change the **Salesperson code** to your initials.  

4.  On the **Navigate** tab, in the **Contact** group, choose **To-dos**.  

5.  On the **Home** tab, in the **Process** group, choose **Create To-do**.  

6.  In the **Create To-do** wizard, add the following information:  

    -   Set the to-do as type **Meeting**.  

    -   Add a short description, such as "discuss proposal."  

    -   Set the meeting for today and add a start time.  

7.  Choose the **Next** button. Your name is displayed as the To-do organizer, and **A. Gibson's Law Firm** as a required attendee.  

8.  Choose the **Finish** button.  

9. In Microsoft Outlook, choose **Calendar** to open the calendar view, and then in the My Calendars list, open your [!INCLUDE[d365fin](includes/d365fin_md.md)] calendar.  

10. On the [!INCLUDE[d365fin](includes/d365fin_md.md)] toolbar, choose the **Synchronize** button to activate synchronization.  

     The synchronization runs, and you can see the appointment that you created on the shared calendar.  

 David checks the synchronized calendar for [!INCLUDE[d365fin](includes/d365fin_md.md)] updates. He sees the appointment and adjusts the time to fix the conflict.  

#### To change a meeting request in [!INCLUDE[d365fin](includes/d365fin_md.md)] and synchronize with Outlook  

1.  In your Outlook calendar, move the appointment created in [!INCLUDE[d365fin](includes/d365fin_md.md)] to another day, and then choose the **Synchronize** button to activate synchronization again.  

2.  Now, open [!INCLUDE[d365fin](includes/d365fin_md.md)] and locate the contact card for CT100006.  

     The **Next To-do Date** field lists the new date of the meeting. You can choose the date field to open the to-do list, and see the changes that you made to the appointment.  

## Handling a Synchronization Conflict  
 Michael decides to call the customer to let the customer know that David has made changes to the appointment. He finds that there is a conflict in the contact information, and troubleshoots the conflict. Although this scenario demonstrates how to solve the conflict manually, you can also set up synchronization to handle conflicts automatically. For more information, see [How to: Set Up Synchronization Conflict Resolution Options](How%20to:%20Set%20Up%20Synchronization%20Conflict%20Resolution%20Options.md).  

#### To handle a conflict  

1.  In Outlook, choose the **Settings** button to open the **Settings** dialog box.  

     The **Settings** dialog box presents several options for resolving conflicts, including options to automatically replace Outlook items with [!INCLUDE[d365fin](includes/d365fin_md.md)] records with Outlook items.  

2.  Select the **Resolve conflicts manually**, and close the **Settings** dialog box.  

3.  In [!INCLUDE[d365fin](includes/d365fin_md.md)], open the contact card for **A. Gibson's Law Firm**, CT100006, and add the telephone number **1234567**.  

4.  Open Outlook and find the contact for **A. Gibson's Law Firm**.  

5.  Change the telephone number to **1224567**, so that it differs from the number that you entered in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

6.  Choose the **Synchronize** button to activate the synchronization.  

7.  Choose the **Troubleshooting** button, and choose the **Conflicts** tab.  

     The conflict is listed here. You can either choose **Show Outlook Item** or **Details** to see more details about the conflict.  

8.  Choose **Details**.  

     The **Conflict Details** dialog box displays a list of the fields that are mapped between the two entities. The conflict is listed in red, which enables you to see that the difference in the telephone number is creating the conflict.  

9. Choose **Replace Outlook Item**, select the item from the list, and then choose the **OK** button.  

## Customizing Synchronization Fields  
 Because ADD INCLUDE<!--[!INCLUDE[demo](includes/demo_md.md)]--> has many foreign contacts and frequently uses the territory code, Michael decides to add this field to the synchronization mapping.  

#### To add fields to the existing setup  

1.  Open [!INCLUDE[d365fin](includes/d365fin_md.md)].  

2.  In the **Search** box, enter **Outlook Synch Entities**, and then choose the related link.  

     The **Outlook Synch. Entity** window contains the definition of the mapping between contacts in [!INCLUDE[d365fin](includes/d365fin_md.md)] and contacts in Microsoft Outlook.  

3.  In the **Code** field, select **CONT_COMP**. On the **Home** tab, in the **Manage** group, choose **Edit**.  

     All the fields that are mapped between the two programs are listed in this window. To add the requested field, add a line in this window and choose the fields that you want to include in the synchronization.  

4.  On the **Navigate** tab, in the **Synch Entity** group, choose **Fields**.  

5.  Choose **New**, and then select **Field No.** 15, Territory Code.  

6.  Because there are no comparable Outlook property to map this to, select the **User Defined** check box for the **Territory Code** field. Choose the **OK** button.  

     Because entries in the Change Log are used to identify changes in [!INCLUDE[d365fin](includes/d365fin_md.md)], you must add this field to the change log as well.  

7.  On the **Navigate** tab, in the **Sync. Entity** group, choose **Register in Change Log Setup**. Choose the **OK** button.  

8.  Choose **OK** again in the dialog box that opens.  

     To make sure that the added territory code appears in Microsoft Outlook, you must create and synchronize a new contact. Changes in the synchronization setup are only shown for newly synchronized items.  

9. In the **Search** box, enter **Contact**, and then choose the related link.  

10. On the **Home** tab, in the **New** group, choose **New**, and create a new contact of the type **Company**.  

11. Add a new customer name.  

12. Expand the **Foreign Trade** FastTab, and then in the **Territory Code** field, select a territory code.  

13. Choose the **OK** button.  

14. Open Microsoft Outlook, and start synchronization.  

15. When the synchronization is finished, in Microsoft Outlook, open the new contact that you created in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

16. On the **Contact** tab, in the **Show** group, choose **All fields** and then select the **User-defined fields in this item** option.  

     Here, you can see that both the salesperson code and the territory code are included in the Outlook contact information.  

     Now that you have completed this walkthrough, you can establish synchronization entities and begin synchronizing between Outlook and your company's [!INCLUDE[d365fin](includes/d365fin_md.md)] implementation.  

## See Also  
 [Outlook Add-in-Product Name Synchronization Add-in](Outlook%20Add-in-($%20P_1%20Product%20Name%20$)%20Synchronization%20Add-in.md)   
 [Troubleshooting: Microsoft Office Outlook Integration and Synchronization](Troubleshooting:%20Microsoft%20Office%20Outlook%20Integration%20and%20Synchronization.md)
