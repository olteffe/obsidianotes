**VS code**

	Ctrl+Shift+P command palette
***

**Привет VSCode**

```bash
python3 -m venv /path/to/new/virtual/environment
source ./venv/bin/activate
deactivate
```
***

**автоактивация venv VSCode**

	<settings.json>
{
    "python.terminal.activateEnvInCurrentTerminal": true,
    "python.pythonPath": "venv/bin/python"    
}
***

**VScode скрыть строку приложения**

You can use this setting to hide the title bar: "window.titleBarStyle": "custom". It can be accessed via menu File → Preferences → Settings → Window → Title Bar Style and set it to custom.
***

**VSCode список расширений**
```bash
codium --list-extensions > VSCodeExtensions.txt
```
***

**golang install in VS code:**
Install go(from golang.go) in ext and run in Ctrl+Shift+p next command: Go: Install/Update Tools
Select all checkbox and Enter
install ext “code runner”
***

**vs code shortcut**
https://blog.logrocket.com/learn-these-keyboard-shortcuts-to-become-a-vs-code-ninja/#:~:text=You%20can%20switch%20between%20views,page%20up%20%2F%20page%20down%20
***

**VS code zsh fonts**
https://stackoverflow.com/questions/62710890/font-issues-while-integrating-zsh-on-visual-studio-code#:~:text=Most%20of%20the,restart%20VS%20Code.

Just set the font to NotoSansMono Nerd Font. This font was already installed on my system. I did not need to download any additional fonts.

There are two ways to change the font in VS Code:

1. Change the following line in settings.json:

	"terminal.integrated.fontFamily": "NotoSansMono Nerd Font"
2. Alternatively, go to Settings -> Features -> Terminal and set Terminal > Integrated: Font Family to:

	NotoSansMono Nerd Font
You may need to restart VS Code.
***

**vs code default shell ->zsh**
When terminal is opened, in top right corner user should click on down-arrow button and then an option menu will appear. Then you should select Select Default Profile and you can choose your default terminal from there.
***
**error  "org.freedesktop.Secret.Collection"**
If the keychain throws the error "No such interface "org.freedesktop.Secret.Collection" on object at path /org/freedesktop/secrets/collection/login", try following the steps described in [issue #92972](https://github.com/microsoft/vscode/issues/92972#issuecomment-625751232) to create a new keyring.

In kubuntu 20, installing `gnome-keyring` was enough for me.

```bash
sudo apt install gnome-keyring
```
***
**Vs code update credentials(token)**
1. Install GitHub CLI on macOS, Windows, or Linux.
2. In the command line, enter "gh auth login", then follow the prompts.
	When prompted for your preferred protocol for Git operations, select HTTPS.
	When asked if you would like to authenticate to Git with your GitHub credentials, enter Y.
***
