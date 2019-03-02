### Fullscreen mode doesn't render properly
Can occur when using DPI scaling above 100%. Can be fixed by disabling DPI scaling in Playnite via `Settings -> Advanced -> Disable DPI Scaling` option.

### Some GOG games appearing as uninstalled in Playnite

Playnite can report some games as "uninstalled" even if they appear installed in Galaxy client. This usually occurs if you import games to Galaxy via "Scan and import folders" feature instead of installing games fresh. Repairing game installations in Galaxy fixes the issue.

### Crash on startup - Windows 7 only

Crash is caused by issue in Microsoft's update for .Net 4.7. Follow instructions from Microsoft's [support page](https://support.microsoft.com/en-us/help/4074906/typeinitializationexception-or-fileformatexception-error-in-wpf-apps-t) or manually install update KB4074906.

### Portable version crashes at startup / during first time setup

Occurs if Microsoft Visual C++ 2013 Redistributable is not installed. [Download](https://www.microsoft.com/en-us/download/details.aspx?id=40784) and install **x86** version to fix the issue.

### Portable version crashes on "access denied" errors or fails to load various dll files

If you used Windows Explorer to unpack portable zip file then Windows might be blocking access to some files. To fix this: Before you unpack the zip file, open its Properties (via right-click menu) and use `Unblock` button.

### Crash on startup

Can be cause by some versions of RivaTunner (or derived apps like MSI Afterburner). To fix the issue either disable GPU acceleration in settings menu (not recommended) or add Playnite to RivaTuner's [exclusion list](https://forums.guru3d.com/threads/excluding-my-application-by-default-rivatuner-causes-latent-crashes.412456/).

### Unable to link accounts, login shows white page

Usually cased either by no internet connection or firewall blocking connection. Make sure that `PlayniteUI.exe` and `CefSharp.BrowserSubprocess.exe` processes are not blocked by firewall.

### UI suttering and mouse lag

Can occur when using G-Sync monitor with "windowed mode" support enabled. To fix the issue either disable GPU acceleration in settings menu (not recommended) or create Playnite profile in Nvidia's control panel and set `Monitor Technology` to `Fixed Refresh`

* Open the NVIDIA Control Panel and navigate to "Manage 3D Settings"
* Select the "Program Settings" tab
* Click "Add" to add a program, and select Playnite
* Change the "Monitor Technology" from "G-SYNC"  "Fixed Refresh"

### UI stuttering when scrolling large lists

Usually caused by slow hard drive or if GPU acceleration is disabled. To mitigate issue make sure that GPU acceleration is enabled and try to enabled `Asynchronous image loading` option. Some improvements are also planned in issue [#454](https://github.com/JosefNemec/Playnite/issues/454)

### Battle.Net games not reported as installed

Some Battle.Net games can be wrongly reported as uninstalled even if Battle.Net client shows them as installed. To fix this open game in Battle.Net client, click `Options` and choose `Scan and Repair`.

### GOG games not reported as installed

Can occur if the game is installed by importing directory into Galaxy client. To fix this open game in Galaxy -> More -> Manage Installation -> Verify / Repair. Then refresh library in Playnite from main menu.

### AuthorizationManager check failed error at startup

If you are using portable version of Playnite then Windows may be blocking loading of some script files. Go to Playnites program folder, under `Scripts` subfolder locate script files reporting AuthorizationManager error, open file properties (via right-click on the file) and unblock the files.

### Extensions menu is grayed out / PowerShell extensions not loading

Occurs on Windows 7 if PowerShell 5 is not installed. [Downloads and install](https://www.microsoft.com/en-us/download/details.aspx?id=54616) PowerShell 5 to fix the issue.

### Error opening database: Unable to cast object of type 'LiteDB.EmptyPage' to type 'LiteDB.DataPage'

In some rare cases database file can get damaged when shutting down Playnite (primarily when using version 4.20 and older).

To fix this issue:
- Download https://playnite.link/download/DbTools.exe
- Place it inside Playnite's installation folder
- Run `DbTools.exe`

It may take a while for tool to finish depending on a size of your library.
If the tool doesn't fix the issue then [database file](https://github.com/JosefNemec/Playnite/wiki/Frequently-Asked-Questions#where-can-i-find-library-file-with-all-games) must be deleted to let Playnite recreate it from skratch.
