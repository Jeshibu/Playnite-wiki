> # **Themming support is currently being [completely reworked](https://github.com/JosefNemec/Playnite/issues/510) for future 5.x versions. It's highly recommend to wait for new system because old themes won't be compatible with new version.**

Playnite uses [XAML](https://msdn.microsoft.com/en-us/library/cc295302.aspx) to create UI views, which means that you don't need to write a single line of code to create new themes.

It's highly recommended that you subscribe to [Theme updates issue #325](https://github.com/JosefNemec/Playnite/issues/325), which is updated every time change is made in Playnite that affects UI themes (added features, localization etc.)

## Quick start
Themes are located in `Skins` folder inside Playnite application folder.

To create new theme:
1. Copy existing theme folder
2. Rename folder and files to follow following structure:
```
<SkinName>
 |-<SkinName>.xaml
 |-<SkinName>.<ProfileName>.xaml
```
3. Edit main `<SkinName>.xaml` file and change `SkinName` string variable to new theme name.
4. Edit all color profiles and change `SkinColorName` string variable.
5. Open Playnite, press `F8` and start testing your new theme.

## Color profiles
Color profiles are designed to provider some customization option, without need to completely rewrite the whole theme.

Lets say that in your `MyTheme.xaml` theme you specify and use `<Color x:Key="TextColor">#f2f2f2</Color>` color. You can then create new `MyTheme.ColorProfile.xaml` and add new definition for that color there. Playnite always loads main theme file first and then profile themes. That means that `TextColor` from the profile file will be applyed because it overrides original value (from main theme file) as it's loaded last.

You can override any object definition in profile file, not just color or brushes.

## Required objects
Themes are required to have some definitions with specific key names because they are used in Playnite views, which are not themeable.

| Object type  | Key name | Description
| ------------- | ------------- | ------------- |
| Brush| TextBrush| Used as default text rendering color
| Brush| TextBrushDark| Usually inverse color of TextBrush, used for rendering on bright backgrounds
| TextBlock style | BaseTextBlockStyle | Style for default textblock objects
| WindowBase style | MainWindowStyle| Style definition of how main Playnite window should look like
| WindowBase style | StandardWindowStyle | Style definition of how all other Playnite windows should look like

## Current limitations
You will not get XAML object completion when editing themes, until you load complete full Playnite source solution in [Visual Studio](https://www.visualstudio.com/vs/community/) (Blend is recommended rather then standard VS, both are in Community edition). After you open the solution file, you will need to add your new theme into `PlayniteUI` project (temporarily while developing it), similarity to how default themes are added.

There's no documentation for model objects and available commands. For now you have to either look at source for [view-model classes](https://github.com/JosefNemec/Playnite/tree/master/source/PlayniteUI/ViewModels) or check how original themes are written.

All style definitions must be in a single file, which makes it a bit messy to edit.

## Help
If you need any help with writing themes then join [Playnite's Discord server](https://discord.gg/hSFvmN6) and ask in `#development` channel.

## Advanced guide

**Coming soon**