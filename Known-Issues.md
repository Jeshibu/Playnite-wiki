### General performance issues and crashes

Custom themes and extensions can greatly affect Playnite's performance and stability. If you start experiencing issues, try switching to default theme and disable 3rd party extensions to see if it fixes the issue. You can quickly test it by starting Playnite in `Safe mode` from Help menu or by using `Safe Mode.bat` from installation folder.

Also make sure that hardware acceleration is not disabled in Advanced -> Performance settings.

### Graphical glitches with hardware acceleration enabled

Can be caused by several things:
- Bad graphics drivers. Try updating/reinstalling GPU drivers.
- Some 3rd party app corrupting rendering. Usually caused by apps that inject overlays. The solution is to add Playnite processes to their exclusion list (if possible) or uninstalled problematic app.

Apps known to cause issues:
- `RivaTuner` and its derivatives like MSI Afterburner, EVGA Precision etc.
- `Nahimic Service`, generally causes issues to a lot of apps and games [including Playnite](https://playnite.link/forum/thread-747.html).

### UI stuttering and mouse lag

Can occur when using G-Sync monitor with "windowed mode" support enabled. To fix the issue create a profile for Playnite processes in Nvidia's control panel and set `Monitor Technology` to `Fixed Refresh`

* Open the NVIDIA Control Panel and navigate to "Manage 3D Settings"
* Select the "Program Settings" tab
* Click "Add" to add a program, and select Playnite
* Change the "Monitor Technology" from "G-SYNC" to "Fixed Refresh"

The same issue can be seen on AMD cards with FreeSync enabled. The issue is [in UI toolkit](https://github.com/dotnet/wpf/issues/2294) we use and so far was not addressed by the developers.

### UI stuttering and mouse lag #2

If you have blur applied to background image (can be changed in the settings), there's known issue with some integrated Intel GPUs that can't handle it properly. You will either need to lower the blur intensity and quality or disable it altogether.

### UI stuttering and mouse lag #3

Intel GPUs have been know to have bad compatibility with some WPF features we use (WPF is UI library Playnite uses). If you have multiple GPUs, make sure that Playnite [is not running](https://www.digitalcitizen.life/set-which-video-cards-are-used-apps-games-windows-10/) on integrated Intel one. Otherwise you may try disabling effect like background blur and transition animations to increase performance.

### UI stuttering when scrolling large lists

Usually caused by slow hard drive or if GPU acceleration is disabled. To mitigate issue make sure that GPU acceleration is enabled and try to enabled `Asynchronous image loading` option. Some improvements are also planned in issue [#454](https://github.com/JosefNemec/Playnite/issues/454)

### Web view component fails to initialize

Usually happens when some program files are missing, damaged or blocked. You can try following to fix the issue:
- Make sure your antivirus doesn't block files from Playnite's installation folder.
- Check that all files are installed correctly, try re-installing Playnite.
- Install [Visual Studio C++ 2019 redistributables](https://aka.ms/vs/17/release/vc_redist.x86.exe) if you are on Windows 7 or 8.
- Choose a different installation location.

### Google Image search doesn't work

Go to Settings -> Advanced and use "Clear web cache".

### Issues with 3rd party libraries

See [separate sections](https://github.com/JosefNemec/Playnite/wiki#3rd-party-libraries) related to each library.

### Play time won't sync

Play time sync is currently supported only by [some library integration plugins](https://github.com/Jeshibu/PlayniteExtensionsFeatures). Playnite also syncs play time only for games that have no time recorded yet (when it's set to 0), otherwise it uses its own internal system to track it. If you want to always force sync from remote account, enable `Prioritize play time for supported libraries` option in general settings.

Also, play time sync only works when import of uninstalled games is enabled and account is connected properly.

### Can't drag and drop .pext and .pthm files into Playnite

If you are running Playnite with elevated user rights (as Administrator), then you can't drop files into it from non-elevated source. This is a Windows security feature. The solution is to not run Playnite as admin or run the source of drag operation as admin.

### Integration logins don't work, show only white/black screen

This is a known issue with Intel Iris Xe GPUs. The solution is to update Intel drivers to newer version. More info [here](https://github.com/dotnet/wpf/issues/3817#issuecomment-857667684). Alternative solution is to disable hardware acceleration in Playnite (Advanced settings section), this is however not recommended since it will negatively impact performance!

### Games disappearing, resetting properties etc.

Happens when syncing Playnite's library files via OneDrive, Google Drive or similar solutions. This is an issue in those cloud apps corrupting or de-syncing Planyite's files. The only solution right now is to make sure that the file sync only happens when Playnite is not running and also that there are never two instances of Playnite running at the same time and using the same cloud files.

### Some metadata are not being downloaded

Causes:

- Metadata download cancelled after games have been imported. You can start new bulk download via Library -> Download metadata menu.
- Metadata download is disabled in general settings -> "Download metadata after importing games".
- Metadata download is configured in a way that doesn't download anything. Check in settings -> Metadata section.
- Installed metadata sources don't provide any metadata. Integration plugins [provide](https://github.com/Jeshibu/PlayniteExtensionsFeatures#official-metadata-support) some metadata for games they import, plus Playnite by default uses [IGDB](https://playnite.link/addons.html#IGDBMetadata_Builtin) to fill in missing data, but it's still possible that some games won't be properly matched in any available metadata sources and will have missing information. In that case:
  - You can edit info manually and use Google Image download to fill in missing media files.
  - You can try installing [metadata plugins](https://playnite.link/addons.html#metadataSources) which can fetch game info from additional sources.

### Cannot authenticate with several accounts after Plynite was updated

Using "Clear web cache" from "Advanced" settings menu will usually fixes the problem.

### Crash on startup - Windows 7 only

Crash is caused by issue in Microsoft's update for .Net 4.7. Follow instructions from Microsoft's [support page](https://support.microsoft.com/en-us/help/4074906/typeinitializationexception-or-fileformatexception-error-in-wpf-apps-t) or manually install update KB4074906.

### Crash on startup

Can be cause by some versions of RivaTunner (or derived apps like MSI Afterburner). To fix the issue either disable GPU acceleration in settings menu (not recommended) or add Playnite to RivaTuner's [exclusion list](https://forums.guru3d.com/threads/excluding-my-application-by-default-rivatuner-causes-latent-crashes.412456/).

### Unable to link accounts, login shows white page

Usually cased either by no internet connection or firewall blocking connection. Make sure that `PlayniteUI.exe` and `CefSharp.BrowserSubprocess.exe` processes are not blocked by firewall.

### AuthorizationManager check failed error at startup

If you are using portable version of Playnite then Windows may be blocking loading of some script files. Go to Playnites program folder, under `Scripts` subfolder locate script files reporting AuthorizationManager error, open file properties (via right-click on the file) and unblock the files.

### Extensions menu is grayed out / PowerShell extensions not loading

Occurs on Windows 7 and 8 if PowerShell 5 is not installed. [Downloads and install](https://www.microsoft.com/en-us/download/details.aspx?id=54616) PowerShell 5 to fix the issue.

### Settings being reset or general data loss

Users reported these issue when installing Playnite via Chocolatey. Chocolatey is not officially supported method of installation/update at the moment and if you are experiencing these issue, use [official methods](https://playnite.link/download.html) of installation instead.

### webp images don't display properly

Install this: https://www.microsoft.com/en-us/p/webp-image-extensions/9pg2dk419drg