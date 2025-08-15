# 🧰 System Setup: C:\Tools, Folder Cleanup & Portable Baseline

## ✅ Summary of What Was Done

### 1. **Removed OneDrive from System Integration**
- Unlinked and terminated OneDrive
- Restored `Documents`, `Pictures`, and `Desktop` to local paths
- Verified all `User Shell Folders` now point to `C:\Users\travi\...`
- Backed up `Documents` and `Pictures` before restoring

### 2. **Created a Portable System Baseline**
- Wrote and saved `backup_shell_folders.ps1` to `C:\Tools`
- Script stores clean local paths for `Documents`, `Pictures`, etc.
- Can be reused on future systems to undo OneDrive integration

### 3. **Built Out `C:\Tools` Environment**
- Moved portable-friendly apps like `Git`, `CPU-Z`, `AIDA64`, and `Speccy`
- Installed CLI tools: `jq`, `ffmpeg`, `neovim`, `ripgrep`, and `fd`
- Verified tool folders are populated and executable

---

## 📁 Scripts Used

### 🔹 backup_shell_folders.ps1

```powershell
$reg = "HKCU:\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders"

$folders = @{
    "Desktop"  = "$env:USERPROFILE\Desktop"
    "Personal" = "$env:USERPROFILE\Documents"
    "MyPictures" = "$env:USERPROFILE\Pictures"
    "MyMusic" = "$env:USERPROFILE\Music"
    "MyVideo" = "$env:USERPROFILE\Videos"
    "{F42EE2D3-909F-4907-8871-4C22FC0BF756}" = "$env:USERPROFILE\Documents"
    "{0DDD015D-B06C-45D5-8C4C-F59713854639}" = "$env:USERPROFILE\Pictures"
    "{AB5FB87B-7CE2-4F83-915D-550846C9537B}" = "$env:USERPROFILE\Pictures\Camera Roll"
}

foreach ($key in $folders.Keys) {
    Set-ItemProperty -Path $reg -Name $key -Value $folders[$key]
    New-Item -ItemType Directory -Path $folders[$key] -Force | Out-Null
    Write-Output "$key set to $($folders[$key])"
}

Write-Output "`n✅ Shell folders configured. Reboot to apply changes."
```

---

### 🔹 Move Portable Apps to `C:\Tools` (No Shortcuts)

```powershell
$appsToMove = @{
    "AIDA64 Extreme" = "C:\Program Files (x86)\FinalWire\AIDA64 Extreme"
    "CPU-Z MSI"       = "C:\Program Files\CPUID\CPU-Z MSI"
    "Git"             = "C:\Program Files\Git"
    "Speccy"          = "C:\Program Files\Speccy"
}

$toolsBase = "C:\Tools"

foreach ($app in $appsToMove.GetEnumerator()) {
    $name = $app.Key
    $source = $app.Value
    $destination = Join-Path $toolsBase $name.Replace(" ", "_")

    if (Test-Path $source) {
        Write-Output "Moving $name..."
        Move-Item -Path $source -Destination $destination -Force
    } else {
        Write-Output "$name not found at $source"
    }
}
```

---

### 🔹 Install Verified CLI Tools (ripgrep & fd)

```powershell
$toolsDir = "C:\Tools"
Set-Location $toolsDir

$downloads = @(
    @{ Name = "ripgrep"; Url = "https://github.com/BurntSushi/ripgrep/releases/download/13.0.0/ripgrep-13.0.0-x86_64-pc-windows-msvc.zip" },
    @{ Name = "fd"; Url = "https://github.com/sharkdp/fd/releases/download/v10.1.0/fd-v10.1.0-x86_64-pc-windows-msvc.zip" }
)

foreach ($tool in $downloads) {
    $name = $tool.Name
    $url = $tool.Url
    $fileName = "$name.zip"
    $targetDir = Join-Path $toolsDir $name

    Write-Output "🔽 Downloading $name..."
    Invoke-WebRequest -Uri $url -OutFile $fileName -UseBasicParsing

    if (Test-Path $targetDir) {
        Remove-Item -Path $targetDir -Recurse -Force
    }

    New-Item -ItemType Directory -Path $targetDir -Force | Out-Null
    Expand-Archive -Path $fileName -DestinationPath $targetDir -Force
    Remove-Item $fileName -Force

    Write-Output "✅ $name installed to $targetDir"
}
```

---

# 🧱 Add C:\Tools Subfolders to System PATH

This script ensures that all subfolders inside `C:\Tools` (e.g., ripgrep, jq, fd) are globally accessible from any terminal session.

---

## ✅ Purpose

Adds each subdirectory of `C:\Tools` to the **system environment variable** `PATH`, allowing you to run tools like `rg`, `jq`, or `fd` without needing to type the full path.

---

## 🛠️ PowerShell Script

> 🟡 **Run as administrator** (required to update system-wide PATH)

```powershell
$toolsRoot = "C:\Tools"
$currentPath = [Environment]::GetEnvironmentVariable("Path", [EnvironmentVariableTarget]::Machine)
$subDirs = Get-ChildItem -Path $toolsRoot -Directory

foreach ($dir in $subDirs) {
    $fullPath = $dir.FullName
```


---


# 🧰 Clean Windows Install Script with Auto PATH Detection

This script:
- Installs your core apps using `winget`
- Sets up `C:\Tools` and installs CLI tools (`jq`, `rg`, `fd`, `neovim`, `ffmpeg`)
- Automatically detects and adds the correct subfolders to system PATH
- Removes OneDrive, Xbox Game Bar, and other bloatware

---

## 🛠️ PowerShell Script

```powershell
# Setup-CleanWindows.ps1

Write-Host "`n🛠️ Starting system setup..." -ForegroundColor Cyan

# Create Tools directory
$toolsDir = "C:\Tools"
New-Item -Path $toolsDir -ItemType Directory -Force | Out-Null
Set-Location $toolsDir

# ---- 1. Install Applications via winget ----
$apps = @(
    "Microsoft.VisualStudioCode",
    "VSCodium.VSCodium",
    "Git.Git",
    "Python.Python.3",
    "Neovim.Neovim",
    "Steam.Steam",
    "PrivateInternetAccess.PrivateInternetAccess",
    "Mozilla.Firefox",
    "Piriform.Speccy"
)

foreach ($app in $apps) {
    Write-Host "📦 Installing $app..." -ForegroundColor Yellow
    winget install --id $app -e --silent
}

# ---- 2. Download CLI Tools (jq, ripgrep, fd, ffmpeg, neovim) ----
$cliTools = @(
    @{ Name = "ripgrep"; Url = "https://github.com/BurntSushi/ripgrep/releases/download/13.0.0/ripgrep-13.0.0-x86_64-pc-windows-msvc.zip" },
    @{ Name = "fd"; Url = "https://github.com/sharkdp/fd/releases/download/v10.1.0/fd-v10.1.0-x86_64-pc-windows-msvc.zip" },
    @{ Name = "jq"; Url = "https://github.com/stedolan/jq/releases/latest/download/jq-win64.exe"; Zip = $false },
    @{ Name = "ffmpeg"; Url = "https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip" },
    @{ Name = "neovim"; Url = "https://github.com/neovim/neovim/releases/latest/download/nvim-win64.zip" }
)

$pathsToAdd = @()

foreach ($tool in $cliTools) {
    $name = $tool.Name
    $url = $tool.Url
    $zip = $tool.ContainsKey("Zip") ? $tool.Zip : $true
    $fileName = "$name.zip"
    $targetDir = Join-Path $toolsDir $name

    Write-Host "🔽 Downloading $name..." -ForegroundColor Yellow
    if ($zip) {
        Invoke-WebRequest -Uri $url -OutFile $fileName -UseBasicParsing
        Expand-Archive -Path $fileName -DestinationPath $targetDir -Force
        Remove-Item $fileName -Force
        $exePath = Get-ChildItem -Path $targetDir -Recurse -Filter "$name.exe" | Select-Object -First 1
        if ($exePath) {
            $pathsToAdd += $exePath.DirectoryName
        }
    } else {
        New-Item -ItemType Directory -Path $targetDir -Force | Out-Null
        Invoke-WebRequest -Uri $url -OutFile "$targetDir\$name.exe" -UseBasicParsing
        $pathsToAdd += $targetDir
    }

    Write-Host "✅ Installed $name to $targetDir" -ForegroundColor Green
}

# ---- 3. Add dynamic paths to system PATH ----
Write-Host "`n🧩 Updating PATH..." -ForegroundColor Cyan
$envPath = [Environment]::GetEnvironmentVariable("Path", [EnvironmentVariableTarget]::Machine)

foreach ($p in $pathsToAdd) {
    if ($envPath -notlike "*$p*") {
        $envPath += ";$p"
        Write-Host "➕ Added to PATH: $p"
    } else {
        Write-Host "✔ Already in PATH: $p"
    }
}

[Environment]::SetEnvironmentVariable("Path", $envPath, [EnvironmentVariableTarget]::Machine)

# ---- 4. Remove Bloatware ----
$bloatApps = @(
    "Microsoft.OneDrive",
    "Microsoft.XboxGameOverlay",
    "Microsoft.XboxGamingOverlay",
    "Microsoft.Xbox.TCUI",
    "Microsoft.XboxSpeechToTextOverlay",
    "Microsoft.YourPhone",
    "Microsoft.GetHelp",
    "Microsoft.Getstarted",
    "Microsoft.ZuneMusic",
    "Microsoft.ZuneVideo",
    "Microsoft.Microsoft3DViewer",
    "Microsoft.MicrosoftSolitaireCollection",
    "Microsoft.MSPaint",
    "Microsoft.People",
    "Microsoft.WindowsFeedbackHub"
)

Write-Host "`n🧹 Removing Bloatware..." -ForegroundColor Red
foreach ($app in $bloatApps) {
    Get-AppxPackage -Name $app -AllUsers | Remove-AppxPackage -ErrorAction SilentlyContinue
    Get-AppxProvisionedPackage -Online | Where-Object DisplayName -EQ $app | Remove-AppxProvisionedPackage -Online -ErrorAction SilentlyContinue
    Write-Host "❌ Removed $app"
}

Write-Host "`n✅ Setup complete! Please reboot to apply all changes." -ForegroundColor Green
```




tags: [system-setup, tools, obsidian, scripts, automation, portability]