---
    title: Specify Colored Indicators to Customize Visual Signals About a Cue's Activity for the Company or Individual Users | Microsoft Docs
    description: As an administrator, you can set up Cues that appear on the users' Role Centers to include an indicator that changes color based on the data values in the Cues.
    services: project-madeira
    documentationcenter: ''
    author: jswymer

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: jswymer

---
# Set Up a Colored Indicator on Cues for the Company or Individual Users
As an administrator, you can set up Cues that appear on the users' Role Centers to include an indicator that changes color based on the data values in the Cues.  
  
The indicator appears as a colored bar along the top border of the Cue tile. It provides a visual signal of the status of the Cue's activity, which can indicate favorable or unfavorable conditions to prompt the user to take action. For example, if a Cue displays ongoing sales invoices, you can set up the indicator to appear green (favorable) when total number of ongoing sales invoices is below 10, and appears red (unfavorable) when the total is greater than 20.  
  
From the **Cue Setup** window, you set up indicators for all the Cues that are available in the company database. You can set up the indicators to apply to all users in the company or an individual user only. The indicator settings in the **Cue Setup** window act as the default indicator settings. If the **Cue Setup End User** window is made available to users, then they can personalize the indicators settings that you define in the **Cue Setup** window.  
  
To set up the indicator, you specify up to two threshold values that define three ranges of data values (low, middle, and high) to which you can apply a different color (or style).  
  
### To set up colored indicators on Cues  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cue Setup**, and then choose the related link.  
  
     The **Cue Setup** window appears. The window lists the indicators that are currently setup up on Cues. Indicators that apply to all users in the company have a blank **User Name** field. Indicators that apply to a specific user include the user's name in the **User Name** field.  
  
    > [!NOTE]  
    >  If you set up a company-wide indicator and a user modifies the indicator later on, then a separate entry for the indicator appears in list for that user.  
  
2. Choose **Edit List** action.  
3. To set up an indicator for a Cue that is not listed in the window, choose the **New** action, and then fill in the fields as described in the following. If you want to modify an existing indicator, go to the next step.  
  
    |  Field  |  Description  |    
    |---------|---------------|  
    |**User Name**|If you want to set up the indicator for all users, leave this field blank.<br /><br /> If you want to set up the indicator for a specific user, then set this field to the user name.|  
    |**Table No**|Specifies the ID of the table object that contains the Cue. Use the drop down list to find the table. The drop down list includes all Cue tables in the company database.<br /><br /> The **Table Name** field will be automatically filled in based on your selection.|  
    |**Field No**|Specifies the ID of the Cue that you want to set up an indicator on. Use the drop down list to find the Cue that you want. **Note:**  The Cue ID corresponds to the field number that is assigned to the Cue in the table. <br /><br /> The **Field Name** field is automatically filled in based on your selection|  
  
4. To set up the indicator for a Cue, set the fields as described in the following table.  
  
    |  Field  |  Description  |    
    |---------|---------------|  
    |**LowStyle**|Specifies the color of the indicator when the Cue's value is below the value of the **Threshold 1** field.|  
    |**LowThreshold**|Specifies the value at or above which the indicator changes to the color specified by the **Middle Range Style** field.|  
    |**MiddleStyle**|Specifies the color of the indicator when Cue's value is greater than or equal to the value of the **Threshold 1** field but less than or equal to the value of the **Threshold 2** field.|  
    |**HighThreshold**|Specifies the value above which the indicator changes to the color specified by the **High Range Style** field.|  
    |**HighStyle**|Specifies the color to use when the Cue's value is above the value of the **Threshold 2** field.|  
  
     The following table lists the colors that correspond to the options of the **LowStyle**, **MiddleStyle**, and **HighStyle** fields.  
  
    |  Option  |  Color  |  
    |----------|---------|  
    |**None**|No color (same color as the Cue tile)|  
    |**Favorable**|Green|  
    |**Unfavorable**|Red|  
    |**Ambiguous**|Yellow|  
    |**Subordinate**|Gray|  
  
## See Also  
[Set Up a Colored Indicator on Cues of Your Workspace](ui-how-setup-colored-indicator-cues.md)  