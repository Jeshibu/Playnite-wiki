### What does Playnite name mean?

Playnite is combination of `Play` and `Unite`.

### How do I backup Playnite library and move it to another PC?

If using portable version, just move the whole installation folder.

If using installed version, then you need to move `%appdata\Playnite\` folder, which contains all user information. Make sure to completely replace the folder on new drive/PC if it already exists from other installation. Just copying over existing user data will cause issues!

### Will there be Linux or macOS version?

Not in near future, mainly for technical reasons. More information [here](https://github.com/JosefNemec/Playnite/issues/59).

### Where can I find library folder with all games?

Go to `Settings` menu and check `Database Location` on `General` tab.

By default for installed versions the library is in `%appdata\Playnite\library` folder and for portable it's just `library` folder inside the application folder.

**Warning: Never combine two different library folders from different Playnite instances. It will generate duplicates in your library. If you are moving library to another Playnite instance always completely replace the folder, never just copy one over another.**

### Where are cover/background images stored?

All media files are stored in `Database Location` directory together with other game information.

### How do I update Playnite?

Playnite supports auto update feature, you don't have to download and install updates manually. Playnite checks for new version at every startup and then every 4 hours. You can also manually check if new version is available by using `Check for Updates` menu option.

### Where are Playnite settings located?

Portable editions have settings stored in `config.json` directly in Playnite's folder. Installed versions store settings in `%AppData%\Playnite\config.json` file.

### How do I unhide game?

Use "funnel" filter button next to the search field to open filter panel, select `Hidden` filter, right-click on hidden game and choose `Show in Library` option.

### How do I convert installed version to portable?

* Shutdown Playnite
* Copy content of `%appdata\Playnite` into Playnite's application folder
* Delete `unins000.exe` and `unins000.dat` files
* Edit `config.json` and change `DatabasePath` property value to `"library"`

### How do I start additional application(s) before game starts and kill it after game exits?

* Edit game and go to `Scripts` tab
* Change runtime to `PowerShell`
* Set first script to start your application using [Start-Process](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/start-process?view=powershell-6) cmdlet
```
Start-Process "c:\somepath\someapp.exe" "-some arguments"
```

* Set second script to kill the application using [Stop-Process](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/stop-process?view=powershell-6) cmdlet

```
Stop-Process -Name "someapp"
```
* If the application requires elevated rights to start then you need to start Playnite as admin too, otherwise the `Stop-Process` will fail due to insufficient privileges.
* If you want to start application minimized and application doesn't have native support for it then add `-WindowStyle` argument.
```
Start-Process "c:\somepath\someapp.exe" "-some arguments" -WindowStyle Minimized
```