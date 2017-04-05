#### This is only basic idea what I would like to focus on. If more people will show interest in developing Playnite I will move to proper project management here on GitHub.

## 0.80

* **In Development** - Better notification bar and progress bar
    * Current implementation moves the whole layout when visible
* **In Development** - More integration and UI tests
* Service login improvements
    * Show successful/unsuccessful login attempts to GOG/Origin in first time wizard and settings windows
    * Offer re-login when library download fails by clicking on notification
* Better update dialog
    * Show changes and new features from last version when Playnite updates
* Options to reset metadata to default values
    * Will re-download game metadata and images from provider site (Steam, GOG etc.) and reset them to default value
* Option to scan folders for bulk addition of games
* Fix up theme (remove unnecessary animations and improve color pallet)
* Add some basic PC info into diagnostics packages (CPU, RAM, OS Version)

## 0.90

* Add additional metadata providers (currently only Wiki) like MobyGames and IGDB
* Speedup initial metadata download (make all provider run in parallel)
* Show (configurable?) more information about game (publishers, release date etc.) on game details view
* Speedup filters with partial reload of the view
* Sorting and filtering for all fileds

## 1.00
* Hi DPI support
    * Rework all popups to use standard menu controls
* Translations
* Download backgrounds for Origin games
* Beta/Supporter branch support with separate updates
* Automatically relaunch when crash occurs (or provider option to do so from crash window)

## Unsorted ideas, without assigned version
* Add non-PC platforms with support for emulators
* Add DOSBox configuration GUI
* Add additional launch options for legacy games (limit CPU cores, CPU speed fix, compatibility flags etc.)
* Automatically detect when 3rd party finishes installing/uninstalling game and update status in Playnite
* Task bar jump list support for last played games
* Option to minimize to tray
* Count play time
    * Maybe display some howlongtobeat.com data?
* Media tab, display internet stuff related to game (news, live streamers, YT videos etc.)