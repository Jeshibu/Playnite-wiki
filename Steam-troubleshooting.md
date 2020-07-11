### Installed games are not detected

Can happen if Steam installation is damaged in some way. Reinstalling Steam fixes the issue.

### Game import fails if Steam's library visibility is set to "Private"

You need to obtain your own [API key](https://steamcommunity.com/dev/apikey) and configure it in Playnite. If Steam asks you for domain name to assign to a key, use any string.

### No games are imported, but no error is shown

It means that you are using private Steam account without providing your own API key. Either provide API key or set account library to `Public` status (`Game details` section in Steam privacy settings).

### Some games not being imported

Playnite is currently unable to import games with `Profiles Features Limited` flag. See issue [#910](https://github.com/JosefNemec/Playnite/issues/910) for more information.

The workaround is:
1) Start installation of such game
2) Update library in Playnite
3) Cancel download or uninstall the game

The game will stay imported and you can change installation status to uninstalled manually.