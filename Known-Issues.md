### Issues with 3rd party libraries

See [separate sections](https://github.com/JosefNemec/Playnite/wiki#3rd-party-libraries) related to each library.

### Some metadata are not being downloaded

For some 3rd party stores we are unable to download all metadata, see [this table](https://github.com/JosefNemec/Playnite/wiki/Feature-table-based-on-library-provider) for more details.

For manually games we fetch metadata from [IGDB database](https://www.igdb.com) based on the game's name. The name matching is not 100% accurate so it may happen that metadata won't be downloaded at all for some games. If that's the case you can manually download metadata from game edit dialog. Also we don't download background images for custom games at all.

### Cannot authenticate with several accounts after Plynite was updated

Using "Clear web cache" from "Advanced" settings menu will usually fixes the problem.

### Crash on startup - Windows 7 only

Crash is caused by issue in Microsoft's update for .Net 4.7. Follow instructions from Microsoft's [support page](https://support.microsoft.com/en-us/help/4074906/typeinitializationexception-or-fileformatexception-error-in-wpf-apps-t) or manually install update KB4074906.

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

### UI suttering and mouse lag #2

If you have blur applied to background image (can be changed in the settings), there's known issue with some integrated Intel GPUs that can't handle it properly. You will either need to lower the blur intensity and quality or disable it altogether.

### UI stuttering when scrolling large lists

Usually caused by slow hard drive or if GPU acceleration is disabled. To mitigate issue make sure that GPU acceleration is enabled and try to enabled `Asynchronous image loading` option. Some improvements are also planned in issue [#454](https://github.com/JosefNemec/Playnite/issues/454)

### AuthorizationManager check failed error at startup

If you are using portable version of Playnite then Windows may be blocking loading of some script files. Go to Playnites program folder, under `Scripts` subfolder locate script files reporting AuthorizationManager error, open file properties (via right-click on the file) and unblock the files.

### Extensions menu is grayed out / PowerShell extensions not loading

Occurs on Windows 7 if PowerShell 5 is not installed. [Downloads and install](https://www.microsoft.com/en-us/download/details.aspx?id=54616) PowerShell 5 to fix the issue.

### Settings being reset or general data loss

Users reported these issue when installing Playnite via Chocolatey. Chocolatey is not officially supported method of installation/update at the moment and if you are experiencing these issue, use [official methods](https://playnite.link/download.html) of installation instead.