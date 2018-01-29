---
    title: Starting the Windows Client at the Command Prompt | Microsoft Docs
    description: You can start the Microsoft Dynamics NAV Windows client at a command prompt. By adding command-line parameters, you can:
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
# Starting the Windows Client at the Command Prompt
You can start the Microsoft Dynamics NAV Windows client at a command prompt. By adding command-line parameters, you can:

* Start the Microsoft Dynamics NAV Windows client with a profile other than the default profile.

* Configure a profile.

* Start the Microsoft Dynamics NAV Windows client with a language other than the default language.

* Start the Microsoft Dynamics NAV Windows client with client settings other than the default client settings.

* Start the Microsoft Dynamics NAV Windows client and open the specified page.

* Start the Microsoft Dynamics NAV Windows client and open the specified report.

To run the Microsoft Dynamics NAV Windows client at a command prompt, open a command-prompt window and locate the Microsoft Dynamics NAV Windows client directory. The default location is C:Program Files (x86)Microsoft Dynamics NAV90RoleTailored Client.

The executable name is:
```
Microsoft.Dynamics.Nav.Client.exe
```
You can also start the Microsoft Dynamics NAV Windows client from the address bar in a browser or from the Run window with the same options. To start the Microsoft Dynamics NAV Windows client from a browser, type the following:

```
DynamicsNAV://<Server/ServerInstance>/<Company>/
```
For example, to open the CRONUS Danmark A/S company, you would enter:

```
DynamicsNAV://localhost/DynamicsNAV90/CRONUS%20International%20Ltd./
```
### Command-Line Parameters
You can use the following parameters when you start the Microsoft Dynamics NAV Windows client at a command prompt.



Parameter  |Description  
---------|---------
-?     |       Displays this list of parameters.  
-configure     | Starts the Microsoft Dynamics NAV Windows client in configuration mode. You use configuration mode to configure a profile. To specify which profile to configure, add the **-profile** parameter.<br/>**Example:**<br/>This command starts the Microsoft Dynamics NAV Windows client in configuration mode for editing the Accounting Manager profile: `Microsoft.Dynamics.Nav.Client.exe -configure -profile:"Accounting Manager"` For more information, see [Open Microsoft Dynamics NAV in Configuration Mode](../how-to-open-microsoft-dynamics-nav-in-configuration-mode.md).       
-debug     |Starts the Microsoft Dynamics NAV Windows client in debug mode.<br/>**Example:**<br/>This command starts the Microsoft Dynamics NAV Windows client in debug mode and runs the **Session List** page so that you can select a session to debug: Microsoft.Dynamics.Nav.Client.exe –debug "DynamicsNAV://localhost:7046/DynamicsNAV90 /CRONUS International Ltd./runpage?page=9506"         
-disablepersonalization     |Disables personalization in the Microsoft Dynamics NAV Windows client. Personalization lets users customize their Role Center and pages by showing or hiding elements such as actions, FactBoxes, FastTabs, and fields.<br/>**Example:**<br/>This command starts the Microsoft Dynamics NAV Windows client with personalization disabled for the Accounting Manager profile: <br/>**NOTE:** You can also disable personalization for users based on their Microsoft Dynamics NAV Windows client profile. For more information, see [Disable Personalization](../how-to-disable-personalization.md).         
-shownavigationpage     |Opens a specific page without displaying the navigation page.<br/>**Example:**<br/>This command starts the Microsoft Dynamics NAV Windows client on page 21 without showing the navigation page.<br/>`Microsoft.Dynamics.Nav.Client.exe -shownavigationpage:0 "DynamicsNAV://Server/Server Instance/Company/RunPage?Page=21"`      
-fullscreen     |Opens a specific page in full-screen mode in Microsoft Dynamics NAV Windows client.<br/>**Example:**<br/>This command starts the Microsoft Dynamics NAV Windows client on page 21 in full-screen mode.<br/>`Microsoft.Dynamics.Nav.Client.exe -fullscreen "DynamicsNAV://Server/Server Instance/Company/RunPage?Page=21"`  
-consolemode     |Starts the Microsoft Dynamics NAV Windows client in console mode to enable running codeunits without any user interface. This is, for example, useful for executing tests.<br/>**Example:**`Microsoft.Dynamics.Nav.CLIENT.exe -consolemode -settings:%DTClientTempPath%ClientUserSettings.config "DynamicsNAV://localhost:7046/DynamicsNav/CRONUS International Ltd./runcodeunit?codeunit=101898" -ShowNavigationPage:0 > %INETROOT%BuildApplicationbuildw1databases_RTC_RunInit.log`<br/>This example runs a test codeunit and writes the result to the _RTC_RunInit.log file.         
-language:id     |Starts the Microsoft Dynamics NAV Windows client with the specified language.<br/>**Examples:**This command starts the Microsoft Dynamics NAV Windows client with locale ID 1033:<br/>`Microsoft.Dynamics.Nav.Client.exe -language:1033`<br/>This command starts the Microsoft Dynamics NAV Windows client for the culture named de-DE:<br/>`Microsoft.Dynamics.Nav.Client.exe -language:de-DE`         
-profile:id     |Starts the Microsoft Dynamics NAV Windows client with the specified profile.<br/>**Example:**<br/>This command starts the Microsoft Dynamics NAV Windows client with the Accounting Manager profile:<br/>`Microsoft.Dynamics.Nav.Client.exe -profile:"Accounting Manager"`        
-settings:file    |Starts the Microsoft Dynamics NAV Windows client with the specified settings file.<br/>For information about Microsoft Dynamics NAV Windows client settings files, see [Configuring the Windows Client](Configuring%20the%20Windows%20Client.md).<br/>**Example:**<br/>This command starts the Microsoft Dynamics NAV Windows client with a version of the ClientUserSettings.config file that is not at the default location:<br/>`Microsoft.Dynamics.Nav.Client.exe -settings:"C:AuxClientSettingsClientUserSettings.config" `        
URL    |Opens the Microsoft Dynamics NAV Windows client to a particular page or with a particular report.<br/>**Examples:**<br/>This command starts the Microsoft Dynamics NAV Windows client and opens to page 21, Customer Card:<br/>`Microsoft.Dynamics.Nav.Client.exe "DynamicsNAV://<Server/ServerInstance>/Company/RunPage?Page=21"`<br/>This command starts the Microsoft Dynamics NAV Windows client and opens the request page for report 101, Customer List:<br/>`Microsoft.Dynamics.Nav.Client.exe "DynamicsNAV://<Server/ServerInstance>/Company/RunReport?Report=101"`<br/>This command runs the same report, assuming the default server, server instance, and company. This version runs from a browser instead of at a command prompt:<br/>`DynamicsNAV:////RunReport?Report=101`<br/>If you specify a server and server instance, then you must also specify a company. You can specify a company without specifying a server and server instance:<br/>`Microsoft.Dynamics.Nav.Client.exe "DynamicsNAV:///Company/RunReport?Report=101"`         
-failurestacktrace    |Sends the stack trace for the Microsoft Dynamics NAV Windows client to the Clipboard.         
-showHelpId    |This command starts Microsoft Dynamics NAV and enables a dialog box which is called each time you press F1. This dialog box displays information about the Help topic that is called from the current page.         

### See Also
[Creating and Running Hyperlinks](Creating%20and%20Running%20Hyperlinks.md)

