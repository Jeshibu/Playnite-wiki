**[Download](https://github.com/JosefNemec/Playnite/releases)**

**Breaking changes**
* Some application settings won't be carried over during update and will be reset to default values
* Changed the way Steam account linking works, re-authentication will be required
* Changed the way Twitch account linking works, re-authentication will be required
* Existing 4.x extensions won't work and will need to be updated by extension author
* Existing 4.x themes won't work anymore
* Changed view naming scheme to correspond with terminology used in Steam
* Name of application executable has changed from `PlayniteUI.exe` to `Playnite.DestkopApp.exe`. There's now also separate `Playnite.FullscreenApp.exe` executable for Fullscreen mode. Things like task bar jumplist won't work properly unless you pin new executable.

**New**
* Completely reworked Fullscreen mode experience (UX design by @LordFren)
* Reworked [custom theme support](https://playnite.link/docs/tutorials/themes/introduction.html)
* Reworked [plugins SDK](https://playnite.link/docs/changelog.html)
* Global game field manager
* Explorer panel
* Numerous improvements to game edit dialog
* Additional grouping, sorting and filtering options
* Options to customize cover image rendering on Grid view (applies to Fullscreen mode as well)
* Options to customize background image rendering (blurring and darkening options as well as separate rendering for game details and window background).
* Options to change position of various panels
* Options to choose which game fields should be displayed on details panel
* Options to save metadata download settings (also configurable from Settings menu)
* Added missing fields that were not being displayed on details view (like scores, age ratings etc.)
* Filters now show list of available items to search by
* Option to import "Last played" information from Steam (by @bburky)
* Less intrusive update notifications (by @Mates1500)
* Option to select different tray icons (by @tylerszabo)
* Origin games sync play time (by @tylerszabo)
* Separate menu for importing Microsoft Store games
* .exe files are now in default list when selecting game icon
* Option to disable XInput handling in Desktop mode
* FightCade emulator profile
* Locale emulator profile
* New translations and translation fixes
* New [command line options](https://github.com/JosefNemec/Playnite/wiki/Cmdline-arguments)

**Fixed**
* Import of uninstalled Twitch games is not working
* Epic store integration is not working properly
* Play time detection is not working for Microsoft Store and Xbox App games (games must be re-imported for fix to work properly)
* Import of Microsoft Store and Xbox App games doesn't work properly
* Time tracking not working properly for Diablo 2 (the game has to be re-imported for fix to work)
* Application can be stuck on exit 
* KeePass use with library authentications keeps entering text in the main Playnite Window (by @tylerszabo)
* Filter textboxes not behaving correctly (by @T-0pel)
* Uninstalled games not being tagged as uninstalled sometimes (by @T-0pel)
* Crash when opening URL (by @tylerszabo)
* Reddit links from IGDB not being imported properly (by @AIRyndon)
* Some strings not being translatable
* Crash when opening .tga image for metadata
* Filter panel state is not saved been application restarts
* Snes9x emulator profile not supporting .smc files
* PCGamingWiki links are not added to all games
* Various crash fixes

Thanks goes to everyone who helped to test new release, everyone contributing patches and also people contributing localizations on our [Crowdin project page](https://crowdin.com/project/playnite).

Special thanks to [Playnite patrons](https://www.patreon.com/playnite) for supporting the project:
* 66dutch
* Adam Jagiełło
* Adam Sunderman
* Al Hunt
* Alex Krastel
* Alex Wu
* Alexander Ulrich
* Alexandre Parent
* Arman Borghem
* Axiomatic
* Bartosz Karla
* Benjamin Jessat
* Blaine Kahle
* Bo Ivarsen
* Brian Robertson
* Bruno B
* Casper Talvio
* Chris Suffern
* Christian Boehme
* christian buzanich
* Clinton Hallahan
* comradek
* Confused Fool
* Connor Dendle
* cosmo bubbles
* Cynamite
* D R
* Daniel Alejandro Liévano
* Daniel Rose
* David
* David B
* David Smedberg
* Donkeyfumbler
* Drew Scheer
* ebeth
* Emma Kloster
* Emmalise Piquette
* Evan Nelson
* FC Ceta
* Ferawyn
* FutureMatt
* GamerGirlAleisha
* Halstead York
* Hardware Scientist
* Jack
* Jack Armstrong
* Jake Gibson
* Jake lasister
* jan forster
* Jared Blum
* Jarvis Smith
* Jason
* Jeff Passarella
* Jens Niehoff
* Jessica
* Joliet Jake
* Jorn Lauwers
* Joseph Dungworth
* Juan-Pierre Flanegan
* Junny
* Jérôme Viéville
* L O' Brien
* Lacy Michelle Irvin
* Leon B.
* Lester Norton
* Luis Fernando Teixeira
* Marcus Sanchez
* MarkusMK
* Mathieu Boyer
* Matthew
* Matthew Minix
* Michael A Gallo
* Michael Good
* Nikolaj Vind Andersen
* Nina Shanafelt
* Ohkami
* OldMan Texas
* outerlimit
* Patrick Hedglen
* Pessimal
* Petr Schreiber
* Petr Soudsky
* Piotr Durlej
* ProPeeves
* pyronectic
* razorrider7
* rindrake
* Ryan Champ
* Sam Stockman
* SaturdayXIII
* Scott Chase
* Scott Walters
* Se7ventySix
* Serv
* Shane Is Games
* Snorezor
* SomeoneElse
* Spencer Diniz
* stephen hendrix
* Stephen Witte
* Stuart Crouch
* stuntaneous
* TechTurtle
* Thomas Maurin
* Tim Trillmann
* Tobias Wiersema
* Tom Weber
* Travis McCoy
* Troy Growden
* Tsahi
* Wohlmeck
* Yassine-Charles Elhadi-Danel