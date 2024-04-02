# New Computer Setup Links and Files
### Browsers
- Chrome - https://www.google.com/chrome/
- Firefox - https://www.mozilla.org/en-US/firefox/windows/
### Dev Tools
- VSCode - https://code.visualstudio.com/download
- Git - https://git-scm.com/downloads
- Sourcetree - https://www.sourcetreeapp.com/
- GitHub Desktop - https://desktop.github.com/
- Notepad++ - https://notepad-plus-plus.org/downloads/
- Docker - https://www.docker.com/products/docker-desktop/
- Kubernetes - https://kubernetes.io/releases/download/
- PuTTY (64-bit 86x) - https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
- Postman - https://www.postman.com/downloads/?utm_source=postman-home
- MySQL Workbench - https://dev.mysql.com/downloads/workbench/
- FileZilla - https://filezilla-project.org/download.php?platform=win64
- Code Fonts - https://github.com/cancng/fonts
- Citrix Workspace - https://www.citrix.com/downloads/workspace-app/
- Node - https://nodejs.org/en/download
- PHP - https://www.php.net/downloads.php
### Misc.
- WinRAR - https://www.win-rar.com/download.html?&L=0
### Personal
- Spotify - https://www.spotify.com/de-en/download/windows/
- OBS Studio - https://obsproject.com/download
- Audio Interface Drivers - https://downloads.focusrite.com/focusrite/scarlett-2nd-gen/scarlett-2i4-2nd-gen


---
## Notes:
### Docker:
If Docker Desktop is stuck in _"Starting the Docker Engine"_:
- Ask IT to add you to the Docker user group
- Open command prompt and run: `wsl --install`
- After installation completes (takes forever), shut down your computer and turn it back on (restart isn't enough)
- Open command prompt or powershell and run `wsl -l -v`
- Set wsl to version 2: `wsl --set-default-version 2`. More optional commands to stop wsl if it is running:
  - `wsl --shutdown`
  - `taskkill /F /IM "Docker Desktop.exe"`
  - `taskkill /F /IM com.docker.backend.exe`
- Open the windows _run_ app from the start menu or with `⊞ Win + r` and type in `optionalfeatures.exe`
- Make sure that `Containers`, `Windows Subsystem for Linux`, `Windows Hypervisor Platform`, and `Virtual Machine Platform` boxes are checked/enabled, and `Hyper-V` is unchecked/disabled.
- Start Docker Desktop and pray

If it still doesn't work, try this:
- Search "Exploit protection" and open it in System settings
- Set "Control Flow Guard (CFG)" to "Off by default"
- Restart your computer
<br></br>
This is another way to do it manually if you don't see that option:
<br></br>
- Switch to "Program settings" tab
- Locate `C:\Windows\System32\vmcompute.exe` in the list, expand it and click edit
  - If it doesn't exist, click "Add program to customize" -> "Choose exact file path" -> add `C:\Windows\System32\vmcompute.exe`
- After you click "Edit" on `C:\Windows\System32\vmcompute.exe`, scroll down to "Control flow guard (CFG)" and uncheck the "Override system settings" option.
- Apply those changes and run powershell or command prompt as admin and run these commands:
  - `net start vmcompute`
  - `wsl --set-default-version 2`
- Start Docker Desktop and pray harder than last time.
<br></br>
If all else fails, you can always use Hyper-V engine instead of WSL2. You can also check the firewall settings, make sure _Virtualization Technology for Directed I/O_ is enabled in the bios, reinstall docker, etc. If you reinstall Docker, make sure you run these commands: 
- `wsl --unregister docker-desktop `
- `wsl --unregister docker-desktop-data`
<br></br>
This was the final solution for me after doing all of the above.
---
### MySQL Workbench Dark Theme
It doesn't support a full dark mode on windows yet, but you can change the code editor theme:
- Go to `C:\Program Files\MySQL\MySQL Workbench 8.0 CE\data`
- Replace the `code_editor.xml` file with the one in this repository
- Or you can find your own online and replace the contents within the `<language name="SCLEX_MYSQL"> </language>` tag
- _(Optional)_ Open MySQL Workbench and go to `Edit` → `Preferences` → `Fonts and Colors` → `Select your scheme` dropdown. You can change this to different windows versions for a slightly different background as well.
### Notepad++ Themes
- Download the Obsidian or Material Theme .xml files from this repository.
- Open the windows _run_ app with `⊞ Win + r` and go to `%APPDATA%\Notepad++`
- Open themes folder, create a new folder named themes if it doesn't exists.
- Place downloaded .xml file(s) inside the folder.
- Restart Notepad++.
- Open Settings -> Style Configurator.
- Select Material Theme from the theme drop-down box.
- Click Save & Close
### Git Bash
If git bash is not starting in the correct user home directory when you first open it (e.g. it shows User.Name@BCLPTP20994 MINGW64 `/` instead of `~`):
- Right click on Git Bash -> Properties
- Replace the "Start in" location with this: `%HOMEDRIVE%%HOMEPATH%`
