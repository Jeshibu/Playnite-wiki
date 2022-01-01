Startup crashes usually happens because of two reasons:

1) Bug in Playnite itself. This is indicated by Playnite showing crash dialog with an ability to send crash report. If this happens, send crash report and open new [bug report](https://github.com/JosefNemec/Playnite/issues).

2) Caused by some 3rd party. This is usually:

- extension or theme. In this case Playnite tries to detect if a crash was caused by an add-on and will show appropriate error about it, but this is always not possible. You can test if an add-on is causing crash by starting Playnite in safe mode (from Help menu or via `Safe Mode.bat` from Playnite's installation folder), or by manually disabling extensions (from add-ons menu) until the crash goes away.

- 3rd party application or system malfunction. This is usually true for crashes that just close Playnite without any crash dialog or error message whatsoever. Usually caused by applications that inject overlays or interact with GPU accelerated apps (and games) in some other manner.