---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# Configure Production Processes
To convert material into produced end items, production resources, such as machine operators and machinery need to be set up in the system.  
  
 Operators and machines are represented in the system as machine centers which are organized into work centers. When these resources are established, they can be loaded with operations according to the item's defined [material and process structure](../FullExperience/define-material-and-process-structure.md), and according to the capacity of the machine or work center. You can also set the production capacity of each resource. Capacity is defined by the work time available in the machine and work centers, and is governed by calendars for each level. A work center calendar specifies the working days or hours, shifts, holidays, and absence that determine the work center’s gross available capacity \(typically measured in minutes\). All of this is determined by defined efficiency and capacity values.  
  
 To learn how the established production resources are used in operations planning and execution, see [Plan for Resource Availability](../FullExperience/execute-production.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Configure the manufacturing features, such as defining shop floor work hours and selecting planning principles.|Manufacturing Setup|  
|Specify which capacity unit, such as minutes or hours, is used to record capacity.|Capacity Unit of Measure|  
|Define a standard working week in terms of starting and ending times of each work day and related work shift.|[How to: Create Work Center Calendars](../FullExperience/how-to-create-work-center-calendars.md)|  
|Organize fixed values and requirements of one production resource to govern the output of production performed in that machine center.|[How to: Set Up Machine Centers](../FullExperience/how-to-set-up-machine-centers.md)|  
|Organize fixed values and requirements of multiple machine centers to govern the output of production performed in that work center.|[How to: Set Up Work Centers](../FullExperience/how-to-set-up-work-centers.md)|  
|Specify the working days or hours, shifts, holidays, and absence that determine the machine or work center’s gross available capacity \(measured in time\) according to its defined efficiency and capacity values.|[How to: Create Work Center Calendars](../FullExperience/how-to-create-work-center-calendars.md)|  
|Plan how machine centers add to the capacity of work centers using consolidated calendars.|[Example - Different Machine Centers Assigned  to a Work Center](../FullExperience/example-different-machine-centers-assigned-to-a-work-center.md)|  
|Group multiple work centers in one department, such as the production department.|[How to: Set Up Work Center Groups](../FullExperience/how-to-set-up-work-center-groups.md)|  
|Define families of production items with similar manufacturing processes.|Family|  
|Specify if expected output quantities should be preset when reporting output.|Preset Output Quantity|  
|Prepare work centers and routings to represent subcontracted production operations.|[About Subcontracting](../FullExperience/about-subcontracting.md)|  
  
## See Also  
 [Plan for Resource Availability](../FullExperience/plan-for-resource-availability.md)   
 [Design and Engineering](../FullExperience/design-and-engineering.md)