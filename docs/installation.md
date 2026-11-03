# Installation

PlayNice runs on 64-bit Windows 11. It installs no driver. For the whole path from download to sound, see [Getting started](getting-started.md).

> **Status:** the steps below describe the 0.1.0 installer. It was exercised in a test virtual machine with one administrator account (a new installation, an upgrade from 0.1.0-beta.2, choosing the folder, the optional removal of your data when uninstalling) and with automated checks. It has not been tested on other Windows builds or languages, with several user accounts, or with a different administrator approving the permission prompt.

## Before you start

- **Microsoft Visual C++ Redistributable 2015-2022 (x64).** Most computers already have it. PlayNice's installer checks for it and warns you if it is missing. If PlayNice reports a missing `VCRUNTIME140` or `MSVCP140` file, install it from Microsoft: <https://aka.ms/vs/17/release/vc_redist.x64.exe>.
- **VB-CABLE** (a separate product from VB-Audio Software, donationware) is needed to send the sound of Windows or of one program to PlayNice. PlayNice's installer does **not** contain, download or install it, and neither does PlayNice. You get it yourself from VB-Audio (<https://vb-audio.com/Cable/>) and run VB-Audio's setup as administrator. You can install PlayNice first: on a new installation, Setup shows a page with these steps when no VB-CABLE is found, and PlayNice's first screen shows them again. See [Getting started](getting-started.md#3-get-vb-cable-from-vb-audio).

## Download

Use the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases) of this repository only, and pick the release you want from the list.

- The installer is named `PlayNice-<version>-Setup-x64.exe`, where `<version>` is the release's version (for example `0.1.0`).
- A release has a `SHA256SUMS.txt` file and its page lists the installer's SHA-256 checksum.

To check the file in PowerShell, replace the name with the file you downloaded:

```powershell
Get-FileHash .\PlayNice-<version>-Setup-x64.exe -Algorithm SHA256
```

Compare the result with the checksum on the release page. A matching checksum shows the file was not damaged or changed after it was published. It does not show that the file is safe.

## Install

1. Run the installer. It shows a short notice first (it says the installer is unsigned and that VB-CABLE is separate).
2. Choose how to install:
   - **Install for all users (recommended).** The default. PlayNice goes into the standard **Program Files** folder (normally `C:\Program Files\PlayNice`) and Windows asks for administrator permission, as it does for most programs. Every account on the computer can then start PlayNice, and each account keeps its own setups and settings.
   - **Install for me only.** No administrator rights are needed. PlayNice goes into `%LOCALAPPDATA%\Programs\PlayNice`, and only your account can use it.
3. On a new installation Setup shows the **destination folder** with a **Browse** button. Keep the suggested folder, or choose another one (a folder with spaces in its name, a non-English name, or one on another drive is fine). Setup refuses a folder that is a drive's root, a Windows or system folder, inside another program's folder, a junction or link, or that already holds other files, and it tells you why.
4. If VB-CABLE was not found, Setup shows a page named **Virtual audio cable** after the folder page, and repeats its steps on the last page, with an unticked option to open VB-Audio's download page. Setup itself installs nothing of VB-Audio's and opens that page only if you tick the option.
5. Leave **Start PlayNice** ticked to open it when Setup finishes, or untick it.

**Choosing a folder for all users.** Programs for all users should not be changeable by ordinary accounts, so Setup protects the PlayNice folder: administrators can change it, everyone else can only read and run it. Setup changes the permissions of that one folder only, never of the folder above it, and refuses a location where it cannot make that safe (for example a folder that an ordinary account owns, or a new folder inside a location that ordinary accounts may rearrange). If you want such a location, choose **Program Files**, pick a parent folder that only administrators can change, or install for yourself only.

Your setups, settings and logs are **not** stored in the installation folder. They stay in the `PlayNice` folder under `%LOCALAPPDATA%` of each Windows account (see [Settings guide](settings-guide.md)), whichever way and wherever PlayNice is installed.

The installer adds a Start menu shortcut, an **Uninstall PlayNice** shortcut and an uninstaller. It does not change your Windows default audio device, does not install a driver itself, and does not turn on starting at sign-in; that is a setting inside PlayNice. PlayNice itself always runs as your ordinary account and never asks for administrator rights.

## Windows warnings

The PlayNice installer is **not yet signed**. Installing it into Program Files does not change that. Windows has features that judge programs it does not know, and they may warn about the installer or block it. The wording depends on your Windows version and settings, and it can change.

What to do:

1. **Check where the file came from.** It must come from this repository's Releases page, and its SHA-256 checksum must match the one on the release page. If either is not true, delete it.
2. **Read the warning.** Windows SmartScreen (a "Windows protected your PC" window) may show **Unknown publisher**. That is expected for an unsigned program. SmartScreen's **More info** shows the file name and publisher. Continuing past a SmartScreen warning is your own decision, per file; it is not something PlayNice can do for you. If the checksum did not match, do not continue.
3. **If Smart App Control blocks it outright**, see [If Smart App Control blocks PlayNice](#if-smart-app-control-blocks-playnice) below. If a work or school policy blocks it, stop there and ask whoever manages the computer, or [report that it was blocked](reporting-a-bug.md#startup-and-installer-problems) with the exact message.
4. **If your antivirus reports a detection** (for example Microsoft Defender names a threat), do not turn Defender off, do not add an exclusion and do not restore a quarantined file. Report it, quoting the name it shows. Do not turn off SmartScreen to get around its warning either; its **More info** page lets you continue per file.

PlayNice's installer never changes Windows security settings.

### If Smart App Control blocks PlayNice

PlayNice is currently **unsigned**. Smart App Control (SAC) is a Windows 11 feature that blocks apps it does not recognise and that have no valid signature, so it may block installing or starting PlayNice. Microsoft says SAC has no exception for a single app.

To see whether SAC is on, open **Windows Security > App & browser control > Smart App Control settings**.

If SAC blocks PlayNice, the safe choice is to wait for a signed release. **PlayNice does not recommend turning Smart App Control off**, and neither PlayNice nor its installer changes it for you. Because SAC has no exception for a single app, running an unsigned program under it would mean turning SAC off for the whole computer and every app, which is a decision about your own computer that only you can make. It does not change Microsoft Defender. Do not turn off Defender or add exclusions.

- If you ever turn SAC off, for your own reasons, note that Microsoft says recent Windows updates let you turn SAC back on later without reinstalling Windows, so keep Windows 11 (25H2 or 26H2) fully updated. On other configurations, for example a managed computer, Windows in S mode, or a build without those updates, turning it back on may need a reset or reinstall of Windows. Microsoft's [FAQ](https://support.microsoft.com/en-us/windows/security/threat-malware-protection/smart-app-control-frequently-asked-questions) does not list every case, so read it before you switch SAC off.
- If the **On** switch is grayed out, install the latest Windows Update first. Microsoft's [October 2026 update note (KB5127648)](https://support.microsoft.com/en-au/servicing/os/windows-11/2026/10/kb5127648-windows-11-24h2-25h2-26h2-security-update) says this was fixed for Windows 11 25H2 and 26H2 by updates released on or after 27 October 2026, and describes a workaround for other cases.

## Upgrade

Run the newer installer. PlayNice keeps its identity, so it replaces the installed copy **in place** and keeps your setups and settings.

- An existing installation keeps its own way of being installed and its own folder. A copy installed for one account **stays** installed for that account (for example a 0.1.0-beta.2 installed for you only is upgraded in place and is not moved to Program Files), and a custom folder is kept. Setup does not ask again.
- Installing 0.1.0 over 0.1.0-beta.2 keeps your setups, settings and start-at-sign-in choice, and removes the two VB-Audio files that earlier installers carried (the driver ZIP and its readme). If you had installed VB-CABLE, it stays.
- Close the PlayNice window first, including its tray icon (the tray menu's **Quit PlayNice**). Setup asks you to if it is open.
- If PlayNice's controller or audio is still running, Setup says so and asks whether to stop it. Continuing **interrupts any sound that is playing**. Choosing not to continue cancels the installation and leaves audio alone.
- **Changing between "for me only" and "for all users" is deliberate, not automatic.** A copy installed one way and a copy installed the other way are treated as different installations: Setup stops, explains, and never removes either by itself. Uninstall the old one first (choose **Keep my data** so your setups remain), then run the installer again and choose the other way. The new installation finds your setups again, because they are stored per account, not with the program.

## Uninstall

Open **Settings > Apps > Installed apps**, find **PlayNice** and choose **Uninstall**, or use **Uninstall PlayNice** in the Start menu (the same uninstaller). Setup asks you to close the PlayNice window first, and asks before it stops audio that is playing.

- Uninstalling shuts down PlayNice's controller and removes PlayNice's sign-in startup entry.
- After you confirm the uninstall, Setup asks one question, which **defaults to keeping everything**. **VB-CABLE is never removed by PlayNice's uninstaller**: it is a separate driver that other programs may use. If it is installed, the last message says it was not touched and where VB-Audio describes how to remove it (<https://vb-audio.com/Cable/>).
  - **Remove your PlayNice data?** **Keep my data** or **Delete my PlayNice data**. Keep it if you may install PlayNice again: your saved setups and settings are then still there. Deleting removes the `PlayNice` folder under `%LOCALAPPDATA%` of **the Windows account you are signed in to**: your saved setups, settings and PlayNice's own logs and diagnostic files. It **cannot be undone** unless you have a backup, and Setup asks you to confirm. It does not touch diagnostic ZIPs you saved elsewhere, other Windows accounts' PlayNice data, or any older Audio Mux data.
- Data is deleted only after PlayNice itself has been removed, and only if Setup can be sure whose data it is. If it cannot (for example a different administrator approved the permission prompt), your data is **kept** and Setup tells you so. If some of it cannot be deleted (a file in use), Setup says so and where the list is; it never claims more than it did.
- For an installation for all users, the uninstall removes the program for everyone but deletes data only for the account that ran it. Other accounts keep their setups; each owner can delete their own `%LOCALAPPDATA%\PlayNice` folder (close PlayNice first).
- A silent uninstall (`/SILENT` or `/VERYSILENT`) asks nothing and keeps your data; VB-CABLE is not touched.
- If you routed a program to **CABLE Input** in Windows, that routing is not undone. See [Windows audio is silent after I stop PlayNice](troubleshooting.md#windows-audio-is-silent-after-i-stop-playnice).

## If installation fails

Note what Setup or Windows showed, which installer file you used, whether you chose **for all users** or **for me only**, and the folder you chose, then [report the problem](reporting-a-bug.md#startup-and-installer-problems).
