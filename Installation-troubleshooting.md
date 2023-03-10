### General download issues

Usually caused by firewall blocking Playnite installer (check firewall settings) or by DNS functionality being broken on ISP's side. For the latter, switch to using CloudFlare's or Google's DNS:

https://developers.cloudflare.com/1.1.1.1/setup/windows/  
https://developers.google.com/speed/public-dns/docs/using#windows

### Can't install into specific folder

Happens if the installer doesn't have permissions to write to selected destination. Use different location if that happens.

### Download fails

Make sure that your Firewall or Anti-malware software is not blocking the installer process.

### General failure

In case of general failure during installation, please let us know by [opening new bug report](https://github.com/JosefNemec/Playnite/issues/new/choose) and use offline installer until the issue is fixed.

### Offline installers

Offline installers can be downloaded from [releases page](https://github.com/JosefNemec/Playnite/releases/latest). Use `exe` file for standard installation and `zip` for portable one. Please note that offline installer is not digitally signed and your AV or browser may report that the file is "potentially dangerous", which is not true.