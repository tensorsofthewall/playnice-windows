# Installation

PlayNice runs on 64-bit Windows 11. It installs no driver and needs no administrator rights for the recommended install.

## Before you start

- **Microsoft Visual C++ Redistributable 2015-2022 (x64).** Most computers already have it. If PlayNice reports a missing `VCRUNTIME140` or `MSVCP140` file, install it from Microsoft: <https://aka.ms/vs/17/release/vc_redist.x64.exe>.
- **VB-CABLE** (a separate product) is needed to send the sound of Windows or of one program to PlayNice. See [Getting started](getting-started.md#2-install-vb-cable-if-you-need-it). You can install PlayNice first.

## Download

Download the installer from the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases) of this repository only. Each release lists the file name and its SHA-256 checksum in `SHA256SUMS.txt`.

To check the file in PowerShell:

```powershell
Get-FileHash .\PlayNice-0.1.0-beta.1-Setup-x64.exe -Algorithm SHA256
```

Compare the result with `SHA256SUMS.txt`. A matching checksum shows the file was not damaged or changed after it was published. It does not show that the file is safe.

## Install

1. Run the installer.
2. Choose **Install for me only** (recommended). No administrator rights are needed.
   **Install for all users** puts the program in the shared Program Files folder and asks for administrator rights. Every account can then start PlayNice, and each account keeps its own setups and settings.
3. Leave **Start PlayNice** ticked to open it when Setup finishes, or untick it.

The installer adds a Start menu shortcut and an uninstaller. It does not change your Windows default audio device, and it does not turn on starting at sign-in; that is a setting inside PlayNice.

## Windows warnings

The PlayNice installer is **not yet signed**, so Windows SmartScreen or Smart App Control may warn about it or block it. Only run an installer you downloaded from this repository's Releases page. Do not turn off Windows security features, and do not add exclusions, to get around a warning. If Windows blocks the installer, [report it](reporting-a-bug.md#startup-and-installer-problems) with the exact message.

## Upgrade

Run the newer installer. PlayNice keeps its identity, so it replaces the installed copy and keeps your setups and settings.

- Quit PlayNice first, including its tray icon.
- Upgrade the same way you installed. A copy installed for one account and a copy installed for all users are treated as different installations, and Setup stops and tells you to uninstall one first. It never removes either by itself.

## Uninstall

Open **Settings > Apps > Installed apps**, find **PlayNice** and choose **Uninstall**. Your setups and settings are kept in the `PlayNice` folder under `%LOCALAPPDATA%` so they are still there if you install again. Delete that folder yourself if you want them gone.

Uninstalling PlayNice does not remove VB-CABLE. Remove it separately, using VB-Audio's instructions.

## If installation fails

Note what Setup or Windows showed, which installer file you used, and whether you chose **for me only** or **for all users**, then [report the problem](reporting-a-bug.md#startup-and-installer-problems).
