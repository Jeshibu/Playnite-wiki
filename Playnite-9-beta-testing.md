!!!IMPORTANT!!!
---------------------

This is a beta test release aimed to to test Playnite 9. It should NOT be used as a "daily driver" since it contains a lot of breaking changes that could potentially contain bugs resulting in data loss! It's also currently not guaranteed that this beta release will be upgradeable to stable one when it's available, although it's likely.

**For that reason, use this beta as a separate installation or install it over portable **copy** of your main Playnite instance.**

Playnite 9 contains a lot of breaking changes to the add-on SDK, which means that none of the existing 3rd party extensions and themes will work until they are updated by their developers.

These builds are also not digitally signed so your browser or anti-malware protection may complain about safety of this build, it's a false positive.

Installation
---------------------

!!! Beta package doesn't come with any built-in integration plugins to test the new add-on download system. You will have to download them after the installation via new Add-ons menu. This only applies to upgrade over existing installs, fresh installations have auto-download built-in into first time startup wizard.

### Clean installations

Just unpack to a folder and start desktop executable.

### Using existing data

If you use installed Playnite version:
- create new [portable copy](https://github.com/JosefNemec/Playnite/wiki/Frequently-Asked-Questions#how-do-i-convert-installed-version-to-portable)
- delete `Extensions` and `Themes` folders from that copy
- unpack beta archive over portable copy

If you use portable Playnite version:
- create copy of your portable installation
- delete `Extensions` and `Themes` folders from that copy
- unpack beta archive over portable copy

Reporting issues
---------------------

If you encounter clear bug, open new issue in this repository, the same way as for stable builds.

General feedback
---------------------

Please use our [Discord server](https://discord.gg/hSFvmN6) for general feedback and questions, specifically `#beta-feedback` channel.

For theme/extension developers
---------------------

See [SDK changelog](https://playnite.link/docs/devel/changelog.html) for list of new and breaking changes. Also read [this page](https://playnite.link/docs/devel/tutorials/playnite9migration.html) for more information about add-on upgrades to new SDK version.

Playnite 9's SDK nuget is only available as a preview release, if you don't see an update to Playnite.SDK package, make sure you have download of preview releases enabled in your IDE.

Download
---------------------

[download link](https://playnite.link/download/Playnite9Beta2.zip)


Beta 2
---------------------

### Installation and download

Use download link from above, it now points to Beta 2 package.

If you have first beta installed, just overwrite files from beta 2 package. If you don't have any beta installed, following original installation instructions.

### Breaking changes

There's a small breaking change in `GameMetadata` class (List based properties are now HashSets). If you are an extensions developer, update to new SDK nuget (preview 4) and make necessary changes to your plugin.

### Beta 2 changelog

New:
* Check for updates menu item checks for add-on updates as well

Fixed:
* Theme style inheritance doesn't work properly
* Minor theme improvements
* Some views don't work in Blend
* Scanning with custom emulator profile fails
* Removing a game from the game options menu in Fullscreen mode leaves you stuck at an empty game details page
* PowerShell script execution fails when running script from network resource
* Platform media is not migrated from Playnite 8
* Fullscreen 'Hidden' and 'Favorite' checkbox filters display wrong games
* Addon browser still lists initial version and release date etc of addon after updating it
* Pressing F11 on Fullscreen mode does not return to desktop mode
* Several crashes

Change log
---------------------

This list is not fully exhaustive, there are many more smaller fixes and improvements in this release.

Breaking:
* Removed IronPython and Batch game script support

New:
* Completely reworked emulation support
* Add-on browser
* Audio feedback and background sound support in Fullscreen mode
* Improved mouse and keyboard navigation in Fullscreen mode
* Plaform, AgeRating, Region and Series fields can hold multiple values
* Completion status is now fully customizable
* Many improvements and new features in SDK
* Improvements to startup speed (library load times)
* Option to switch to Fullscreen from tray menu
* Option to install add-ons via Playnite URI
* Configurable buttons on top panel
* Option to cancel library update in Fullscreen mode
* URI command to open on specific game details
* Support for game variables in game manual field
* Show images dimensions in metadata comparison window
* Scroll behaviour and layout options for Grid view
* Playnite API and game object accessible in game scripts
* Option to swap X/A button on main FS screen
* Option to specify monospaced font (used by some text fields like scripts)
* Option to save filter presets
* Option to reset application settings to default
* Option to not minimize Fullscreen app after starting a game
* Option to keep main menu on top panel if sidebar is visible
* Option to change play time tracking mode
* Option to change font sizes in Fullscreen mode
* Option to hide some items from Fullscreen main menu
* Option to hide mouse cursor in Fullscreen mode
* Option to show software tools on Sidebar
* Option to force Fullscreen mode to always use primary display
* Option to enable async image loading in Fullscreen mode
* Option to disable XInput support in Fullscreen mode
* Option to assign partial release dates
* Image rendering quality/performance scaling options
* Game groups on Grid view
* Button to test game scripts
* Allow multiple Play actions
* Import exclusion are stored in game library files
* Support to search for specific resolutions during google image searches and added resolution presets.
* Show address bar on WebView windows
* Game scripts now share one runtime instance allowing them to share data between various events

Fixed:
* Playnite's library data are now stored in less files and they are locked while Playnite is running. This should fix data corruption issues when syncing Playnit's files via could storage solutions.
* Mouse scrolling doesn't work properly in FS mode
* Sorting name is ignored when grouping by name
* Prevent updating game library entries during library update when no data has changed
* Game menu not visible fully under some circumstances
* Don't prevent wake events when suspending/hibernating Windows from Playnite
* "Recently played" tab in Fullscreen Mode doesn't update after launching game
* Race condition during addon installation
