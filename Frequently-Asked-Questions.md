### Preamble

If you see any path on this page that starts with `%appdata%` or `%localappdata%`, then copy that path exactly as written and paste it into your file explorer to navigate to a correct directory. Strings starting and ending with `%` are environment variables that will be properly converted when you tell your file explorer to navigate there.

### What does Playnite name mean?

Playnite is a combination of `Play` and `Unite`.

### Can I link multiple accounts?

You can't, unless a library integration plugin explicitly supports it (gives you an option to link multiple accounts).

You can however link one account, import games, link a different account, import games again and you'll end up with a library that contains games from both accounts. Playnite never automatically removes games from the library so linking a different account won't affect games from other accounts in any way.

### What is Safe Mode?

Safe Mode starts Playnite with all 3rd party extensions disabled and using only default theme.

You can start safe mode via `Safe Mode.bat` from Playnite's installation directory or by using `--safestartup` argument when starting Playnite's executable.

### I'm getting warning about elevated privileges

Playnite will show warning if it detects itself running with elevated privileges. We show this warning because these privileges are inherited to all installed extensions and to everything you subsequently start from Playnite (all games and apps).

Playnite itself **doesn't** require elevated privileges to function properly so it's an unnecessary security risk to run it that way.

You may get this dialog in several cases, some examples include:

- If Playnite is launched as admin, either manually or via compatibility flag.
- Application that's starting Playnite is already running with elevated privileges.
- You have UAC completely disabled in User Account Control Windows settings.
- You installed Playnite using unsupported method that forces it to run elevated. For example people installing using Chocolatey reported this issue.

### How do I backup Playnite library and move it to another PC?

Playnite 10 introduced built-in options to backup and restore Playnite data accessible from the Library menu.

To manually backup data:

- If using portable version, just move the whole installation folder.
- If using installed version, then you need to move [%appdata%\Playnite](#Preamble) folder, which contains all user information.

Make sure to completely replace the folder on new drive/PC if it already exists from other installation. Just copying over existing user data will cause issues!

### Does Playnite support X controller?

[[Gamepad-Controller-support]]

### Will there be Linux or macOS version?

Not in near future, mainly for technical reasons. More information [here](https://github.com/JosefNemec/Playnite/issues/59).

### Where can I find library folder with all games?

Go to `Settings` menu and check `Database Location` on `Advanced` tab.

By default for installed versions the library is in [%appdata%\Playnite\library](#Preamble) folder and for portable it's just `library` folder inside the application folder.

**Warning: Never combine two different library folders from different Playnite instances. It will generate duplicates in your library. If you are moving library to another Playnite instance always completely replace the folder, never just copy one over another.**

### Where are cover/background images stored?

All media files are stored in `Database Location` directory together with other game information.

### How do I update Playnite?

Playnite supports auto update feature, you don't have to download and install updates manually. Playnite checks for new version at every startup and then every 4 hours. You can also manually check if new version is available by using `Check for Updates` menu option.

### Where are Playnite settings located?

Portable editions have settings stored in `config.json` directly in Playnite's folder. Installed versions store settings in [%AppData%\Playnite\config.json](#Preamble) file.

### My games are not importing
1. Check that your library plugin is configured and authenticated correctly via `main menu > Add-ons > Extension settings > Libraries` - make sure especially that uninstalled games are set to import if that setting is available
2. Make sure that you're logged into the right account with the library plugin
3. Check if the game is present in `main menu > Settings > Import exclusion list`

### My games are gone
1. **Filtered**: Does it say "Filter enabled" in the top bar? If so, right click that text, or enable the filter panel with `ctrl+G` and click `Clear filters` at the top
2. **Hidden**: In the filter panel, check the `Hidden` checkbox

### How do I unhide game?

Use "funnel" filter button next to the search field to open filter panel, select `Hidden` filter, right-click on hidden game and choose `Show in Library` option.

### How do I convert installed version to portable?

1. Shutdown Playnite
2. Copy content of [%appdata%\Playnite](#Preamble) into Playnite's application folder
3. Delete `unins000.exe` and `unins000.dat` files
4. Edit `config.json` and change `DatabasePath` property value to `"library"`

### How do I start additional application(s) before game starts and kill it after game exits?

See [this page](https://github.com/JosefNemec/Playnite/wiki/Game-scripts).
