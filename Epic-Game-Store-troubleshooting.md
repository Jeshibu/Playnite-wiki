### "pollingId is invalid" error when logging in

Currently [known issue](https://github.com/JosefNemec/Playnite/issues/1416) when using 3rd party services (Google for example) to sing in into Epic account. The only solution right now is to [setup password](https://github.com/JosefNemec/Playnite/issues/1416#issuecomment-534890200) on your Epic account.

### Game doesn't start properly 

Some games might not start properly when option to start game without Epic launcher is enabled.

In that case: 
- Edit the game and go to "Actions" tab
- Uncheck "Managed by library plugin" option
- Set play action to "URL" type and set path to `com.epicgames.launcher://apps/<gameid>?action=launch&silent=true`, where replace `<gameid>` with game's id you can find on "Advanced" tab.

### Changing only specific games to run without Epic client

You can set only specific games to run directly without Epic client. To do so:

- Edit then game and go to "Actions" tab
- Uncheck "Managed by library plugin" option
- Set play action to "Executable" type
- Change "Path" variable to game's executable path
