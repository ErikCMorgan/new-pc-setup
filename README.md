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
- Make sure that `Windows Subsystem for Linux` and `Virtual Machine Platform` boxes are checked.
- Start Docker Desktop and pray

If all else fails, you can always use Hyper-V engine instead of WSL2. You can also check the firewall settings, make sure _Virtualization Technology for Directed I/O_ is enabled in the bios, reinstall docker, etc.

### MySQL Workbench Dark Theme
It doesn't support a full dark mode on windows yet, but you can change the code editor theme:
- Go to `C:\Program Files\MySQL\MySQL Workbench 8.0 CE\data`
- Replace the `code_editor.xml` file with the one in this repository
- Or you can find your own online and replace the contents within the `<language name="SCLEX_MYSQL"> </language>` tag
- _(Optional)_ Open MySQL Workbench and go to `Edit` → `Preferences` → `Fonts and Colors` → `Select your scheme` dropdown. You can change this to different windows versions for a slightly different background as well.
