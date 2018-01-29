## Adding new language
**Check if language is already being worked on via [this list](https://github.com/JosefNemec/Playnite/issues?q=is%3Aopen+is%3Aissue+label%3Alocalization)**

1. Copy and rename English localization file `english.xaml` from `Localization` folder

2. Edit new file and change following strings:
   * `LocalizationLanguage` - should be the same as name of new file without extension
   * `LocalizationString` - display string of new language (will be visible in settings window when changing language)

3. Translate all strings in new file
   * **Keep formating of strings marked with `xml:space="preserve"`, especially new lines and white spaces. Otherwise text may not display properly in application.**

4. Start Playnite and test that new localization file works properly

5. [Open new issue](https://github.com/JosefNemec/Playnite/issues) and attach new localization file there. Issue will be notified when new strings are added into Playnite for translation.

6. Subscribe to [localization updates](https://github.com/JosefNemec/Playnite/issues/385) issue, to be notified when English strings are being added/updated to update your translation.

## Updating existing language

To automatically update localization file with new strings (after new Playnite update adds new strings into english.xaml), do following (you don't have to use the script, you can also update the file manually):

1. Download [UpdateLocFiles.ps1](https://github.com/JosefNemec/Playnite/blob/master/scripts/UpdateLocFiles.ps1) script

2. If this is first time you are running PowerShell script, start PowerShell as administrator and type following: `Set-ExecutionPolicy Unrestricted`

3. Execute script with following parameters:
   * `SourceDictionary` - full path to `english.xaml` file
   * `TargetDictionary` - full path to localization file that should be updated with new strings

Example:

`.\UpdateLocFiles.ps1 -SourceDictionary "c:\Playnite\Localization\english.xaml" -TargetDictionary "c:\Playnite\Localization\czech.xaml"`

4. Localization file should be now updated with all missing strings from original English version