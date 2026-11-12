## VS Code

### Export

**On macOS / Linux:**

```bash
cd /path/to/your-repo

code --list-extensions > extensions.txt

cp ~/Library/Application\ Support/Code/User/settings.json .
cp ~/Library/Application\ Support/Code/User/keybindings.json .
```

**On Windows (PowerShell):**

```powershell
cd C:\path\to\your-repo

code --list-extensions > extensions.txt

Copy-Item "$env:APPDATA\Code\User\settings.json" .
Copy-Item "$env:APPDATA\Code\User\keybindings.json" .
```

### 3. Import

**On macOS / Linux:**

```bash
cp settings.json keybindings.json ~/Library/Application\ Support/Code/User/

cat extensions.txt | xargs -n 1 code --install-extension
```

**On Windows (PowerShell):**

```powershell
Copy-Item settings.json, keybindings.json "$env:APPDATA\Code\User\"

Get-Content extensions.txt | ForEach-Object { code --install-extension $_ }
```
