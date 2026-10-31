# Installation

PlayNice runs on 64-bit Windows 11. It installs no driver and needs no administrator rights for the recommended install. For the whole path from download to sound, see [Getting started](getting-started.md).

> **Status:** the first public beta, [v0.1.0-beta.1](https://github.com/tensorsofthewall/playnice-windows/releases/tag/v0.1.0-beta.1), is published on the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases) as a Pre-release. The steps below describe its installer. The maintainer reports that one installed copy passed native sign-in, tray and Explorer-recovery checks (see [Start at sign-in](settings-guide.md#start-at-sign-in)); the exact installer file of that copy was not recorded. Installation has not been tested on a clean computer or with more than one user account.

## Before you start

- **Microsoft Visual C++ Redistributable 2015-2022 (x64).** Most computers already have it. PlayNice's installer checks for it and warns you if it is missing. If PlayNice reports a missing `VCRUNTIME140` or `MSVCP140` file, install it from Microsoft: <https://aka.ms/vs/17/release/vc_redist.x64.exe>.
- **VB-CABLE** (a separate product) is needed to send the sound of Windows or of one program to PlayNice. See [Getting started](getting-started.md#2-download-vb-cable-from-the-official-site). You can install PlayNice first. PlayNice's installer does not install it.

## Download

Use the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases) of this repository only, and pick the release you want from the list.

- While PlayNice is in beta its releases are marked **Pre-release**. GitHub's "latest release" link skips pre-releases, so this documentation links to the full list instead.
- The installer is named `PlayNice-<version>-Setup-x64.exe`, where `<version>` is the release's version (for the first beta, `0.1.0-beta.1`).
- A release's page lists the installer's file name and its SHA-256 checksum.

To check the file in PowerShell, replace the name with the file you downloaded:

```powershell
Get-FileHash .\PlayNice-<version>-Setup-x64.exe -Algorithm SHA256
```

Compare the result with the checksum on the release page. A matching checksum shows the file was not damaged or changed after it was published. It does not show that the file is safe.

## Install

1. Run the installer. It shows a short beta notice first.
2. Choose **Install for me only** (recommended). No administrator rights are needed.
   **Install for all users** puts the program in the shared Program Files folder and asks for administrator rights. Every account can then start PlayNice, and each account keeps its own setups and settings.
3. Leave **Start PlayNice** ticked to open it when Setup finishes, or untick it.

The installer adds a Start menu shortcut and an uninstaller. It does not change your Windows default audio device, does not install a driver, and does not turn on starting at sign-in; that is a setting inside PlayNice.

## Windows warnings

The PlayNice installer is **not yet signed**. Windows has features that judge programs it does not know, and they may warn about the installer or block it. The wording depends on your Windows version and settings, and it can change.

What to do:

1. **Check where the file came from.** It must come from this repository's Releases page, and its SHA-256 checksum must match the one on the release page. If either is not true, delete it.
2. **Read the warning.** Windows SmartScreen (a "Windows protected your PC" window) may show **Unknown publisher**. That is expected for an unsigned program. SmartScreen's **More info** shows the file name and publisher. Continuing past a SmartScreen warning is your own decision, per file; it is not something PlayNice can do for you. If the checksum did not match, do not continue.
3. **If Smart App Control blocks it outright**, see [If Smart App Control blocks PlayNice](#if-smart-app-control-blocks-playnice) below. If a work or school policy blocks it, stop there and ask whoever manages the computer, or [report that it was blocked](reporting-a-bug.md#startup-and-installer-problems) with the exact message.
4. **If your antivirus reports a detection** (for example Microsoft Defender names a threat), do not turn Defender off, do not add an exclusion and do not restore a quarantined file. Report it, quoting the name it shows. Do not turn off SmartScreen to get around its warning either; its **More info** page lets you continue per file.

PlayNice's installer never changes Windows security settings.

### If Smart App Control blocks PlayNice

PlayNice is currently **unsigned**. Smart App Control (SAC) is a Windows 11 feature that blocks apps it does not recognise and that have no valid signature, so it may block installing or starting PlayNice. Microsoft says SAC has no exception for a single app.

To see whether SAC is on, open **Windows Security > App & browser control > Smart App Control settings**.

If SAC blocks PlayNice, you can wait for a signed release or, if you choose, turn SAC **Off** there. That is your decision. It turns SAC off for the whole computer and every app, not just PlayNice, and it does not change Microsoft Defender. Do not turn off Defender or add exclusions.

- Microsoft says recent Windows updates let you turn SAC back on later without reinstalling Windows, so keep Windows 11 (25H2 or 26H2) fully updated. On other configurations, for example a managed computer, Windows in S mode, or a build without those updates, turning it back on may need a reset or reinstall of Windows. Microsoft's [FAQ](https://support.microsoft.com/en-us/windows/security/threat-malware-protection/smart-app-control-frequently-asked-questions) does not list every case, so read it before you switch SAC off.
- If the **On** switch is grayed out, install the latest Windows Update first. Microsoft's [October 2026 update note (KB5127648)](https://support.microsoft.com/en-au/servicing/os/windows-11/2026/10/kb5127648-windows-11-24h2-25h2-26h2-security-update) says this was fixed for Windows 11 25H2 and 26H2 by updates released on or after 27 October 2026, and describes a workaround for other cases.

## Upgrade

Run the newer installer. PlayNice keeps its identity, so it replaces the installed copy and keeps your setups and settings.

- Close the PlayNice window first, including its tray icon (Quit GUI). Setup asks you to if it is open.
- If PlayNice's controller or audio is still running, Setup says so and asks whether to stop it. Continuing **interrupts any sound that is playing**. Choosing not to continue cancels the installation and leaves audio alone.
- Upgrade the same way you installed. A copy installed for one account and a copy installed for all users are treated as different installations, and Setup stops and tells you to uninstall one first. It never removes either by itself.

## Uninstall

Open **Settings > Apps > Installed apps**, find **PlayNice** and choose **Uninstall**. Setup asks you to close the PlayNice window first, and asks before it stops audio that is playing.

- Uninstalling shuts down PlayNice's controller and removes PlayNice's sign-in startup entries.
- Your setups and settings are kept in the `PlayNice` folder under `%LOCALAPPDATA%` so they are still there if you install again. Delete that folder yourself if you want them gone.
- Uninstalling PlayNice does not remove VB-CABLE. Remove it separately, using VB-Audio's instructions.
- If you routed a program to **CABLE Input** in Windows, that routing is not undone. See [Windows audio is silent after I stop PlayNice](troubleshooting.md#windows-audio-is-silent-after-i-stop-playnice).

## If installation fails

Note what Setup or Windows showed, which installer file you used, and whether you chose **for me only** or **for all users**, then [report the problem](reporting-a-bug.md#startup-and-installer-problems).
