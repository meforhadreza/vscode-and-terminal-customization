# operator-mono-lig
A custom font using Operator Mono and Fira-Code styled ligatures.

### Usage (VS Code)

```"editor.fontFamily": "'Operator Mono SSm Lig','Operator Mono Lig','Fira Code'```

```"editor.fontWeight": "300" //adjust as per need```

# For terminal
1. install oh-my-posh
2. copy custom theme to oh-my-posh theme directory
3. persist the current theme 
4. set 'Hack Nerd Font' in teminal settings for better icon support. also set it in vscode settings.json

```"terminal.integrated.fontFamily": "'Hack Nerd Font'"```


# Oh My Posh Installation Guide (Windows)

## 1. Install Oh My Posh

```powershell
winget install JanDeDobbeleer.OhMyPosh --source winget
```

---

## 2. Create Theme Directory

Store your custom theme configuration in:

```text
C:/Users/Reza/.config/ohmyposh/reza.omp.json
```

Create the directory if it does not exist:

```powershell
mkdir C:\Users\Reza\.config\ohmyposh
```

---

# PowerShell Setup (This process must be done seperatly from Powershell 7 and 5 profile)

## 3.1 Create PowerShell Profile

```powershell
New-Item -Path $PROFILE -Type File -Force
```

## 3.2 Open Profile

```powershell
notepad $PROFILE
```

Add the following line:

```powershell
oh-my-posh init pwsh --config "C:/Users/Reza/.config/ohmyposh/reza.omp.json" | Invoke-Expression
```

Save and close the file.

## 3.3 Allow Profile Execution

Run:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Restart PowerShell.

---

# Git Bash Setup

Open `.bashrc`:

```bash
nano ~/.bashrc
```

Add:

```bash
eval "$(oh-my-posh init bash --config 'C:/Users/Reza/.config/ohmyposh/reza.omp.json')"
```

Save and exit.

Reload the configuration:

```bash
source ~/.bashrc
```

Restart Git Bash if necessary.

---

# CMD Setup (Clink Required)

## 5.1 Find Clink User Scripts Directory

Run:

```cmd
clink info
```

Locate the **User Scripts** directory from the output.

## 5.2 Create Lua Initialization File

Create a file named:

```text
oh-my-posh.lua
```

inside the User Scripts directory.

## 5.3 Configure Oh My Posh

Add the following content to `oh-my-posh.lua`:

```lua
load(io.popen('oh-my-posh init cmd --config "C:/Users/Reza/.config/ohmyposh/reza.omp.json"'):read("*a"))()
```

Restart CMD.

---

# Theme Location

```text
C:/Users/Reza/.config/ohmyposh/reza.omp.json
```

---

# Useful Commands

### Check Oh My Posh Version

```powershell
oh-my-posh version
```

### List Available Themes

```powershell
Get-ChildItem "$env:POSH_THEMES_PATH"
```

### Export a Theme

```powershell
oh-my-posh print primary
```

### Reload PowerShell Profile

```powershell
. $PROFILE
```

---

# Installed Shell Integrations

| Shell       | Status |
| ----------- | ------ |
| PowerShell  | ✅      |
| Git Bash    | ✅      |
| CMD (Clink) | ✅      |

All shells use the same theme file:

```text
C:/Users/reza/.config/ohmyposh/reza.omp.json
```
