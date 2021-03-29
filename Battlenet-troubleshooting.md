### Authentication being lost after some time
This is a battle.net issue, it likes to invalidate logging session way too soon. For now I recommend syncing your library and then switching settings back to syncing only installed games. You will need to switch to full sync only when you add new game to your account. More information available [here](https://github.com/JosefNemec/Playnite/issues/1057).

### Games not reported as installed

Some Battle.Net games can be wrongly reported as uninstalled even if Battle.Net client shows them as installed. To fix this open game in Battle.Net client, click `Options` and choose `Scan and Repair`.

### Newly published game not being imported

Games from battle.net integration have to be supported one by one. This means that newly published games on the platform won't be supported in Playnite until the integration plugin is updated (with explicit support for those new games). You will need to import those games manually until update is released.