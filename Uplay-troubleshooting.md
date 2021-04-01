### Uplay client not being detected

Reinstall Uplay client to fix the issue.

### Uninstalled games not importing properly
Uplay client has to be started at least once (and user must be logged in) for Playnite to import all games properly. Uplay doesn't have to be running for import to work, only initial authentication in Uplay is important.

If you are still having issues then try deleting `c:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\cache\configuration\configurations` file, restarting Uplay and then try import in Playnite again. 

### Newly bought games not being imported
Uplay has to be started at least once after new game is added to your account for Playnite to properly recognize it.

### Games not imported

Games that were bought from a different store (like Steam), but require Ubisoft Connect to launch, won't be imported. It's done that way because launching those from Ubisfot Connect still requires that original launcher (Steam for example) to be installed and it would create unnecessary duplocates. Only Ubisoft games bought on Ubisoft store or those that don't require 3rd party launcher to start, will be imported.