### General

Make sure that your firewall is not blocking `PlayniteUI.exe` and `CefSharp.BrowserSubprocess.exe` processes. Both must be allowed in firewall settings.

### Steam

Steam accounts are by default set to private library visibility. This means that Playnite will not be able to download list of library games. To fix it there are two options:

- Set library visibility to public by setting `Game details` privacy option to `Public` (under `My Privacy Settings` when editing Steam profile page).

- Obtaining private API key if you want to keep using private account visibility. You can [obtain API key](https://steamcommunity.com/dev/apikey) from Valve and set it in Playnite's account settings.

### GOG

Syncing via `Account Name` option only works if privacy setting `Your full game library can be seen by` option is set to `All Visitors` (under `Privacy & settings` -> `Privacy` menu on GOG's website).

To use private account you need to use `Account Login` option and authenticate your account.

### Battle.net

There's a [known issue](https://github.com/JosefNemec/Playnite/issues/234) with Battle.net login session expiring and Playnite requiring re-authentication. Until the issue is solved we recommend syncing your library once and then switching settings back to syncing only installed games. You will then need to switch to full sync only when new game is added to your account.

### itch.io

Official [Itch client](https://itch.io/app) version 25 and newer must be installed for Playnite to properly sync itch.io library. Older Itch clients [might not automatically update](https://github.com/JosefNemec/Playnite/issues/107#issuecomment-461964182) to v25 and manual re-installation might be required.

### Twitch

There's a [known issue](https://github.com/JosefNemec/Playnite/issues/991) with some specific accounts not being able to sync with Playnite. There's currently no solution.

### Epic Store

If you don't use password to sign-in into Epic account (for example by using Google sign-in) you can encounter `pollingId is invalid` error. [Solution is](https://github.com/JosefNemec/Playnite/issues/1416#issuecomment-531552248) to add password to your account and login in Playnite using password.