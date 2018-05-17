Scripts (`.py` or `.ps1` files) or plugins (`.dll` files) are installed into Playnite by placing them into correct directory.

### Scripts
When using portable version of Playnite script files are stored in Playnite's program folder inside `\Scripts\PowerShell` folder for PowerShell scripts (`.ps1` files) and `\Scripts\IronPython` for IronPython scripts (`.py` files). Only scripts placed directly inside the script folder are loaded, any scripts inside additional subfolders are ignored.

When using installed version of Playnite place scripts inside `%AppData%\Playnite\` folder instead of program folder while keeping the same structure based on used script language.

*After installing script you don't have to restart Playnite for it to be loaded. Use `Tools` -> `Reload scripts` menu to initialize new scripts and reload updated ones.*

### Plugins

When using portable version of Playnite plugin files (`.dll` files) are stored in Playnite's program folder inside `Plugins` subfolder. Only plugins placed directly inside the plugins folder are loaded, any plugins inside additional subfolders are ignored. When using installed version of Playnite place plugins inside `%AppData%\Playnite\Plugins\` folder.

*Unlike scripts adding new plugins requires Playnite to be restarted for plugins to load properly.*