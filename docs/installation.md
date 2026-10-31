# Installation

PlayNice runs on 64-bit Windows 11. It installs no driver and needs no administrator rights for the recommended install. For the whole path from download to sound, see [Getting started](getting-started.md).

> **Status:** the first beta has not been published yet. Until it is, the [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases) has no installer and there is nothing to install. The names and steps below describe the beta installer. The maintainer reports that one installed copy passed native sign-in, tray and Explorer-recovery checks (see [Start at sign-in](settings-guide.md#start-at-sign-in)); the exact installer file of that copy was not recorded. Installation has not been tested on a clean computer or with more than one user account.

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
3. **If Smart App Control or another policy blocks it outright** and offers no way to continue, stop there. Do **not** turn Smart App Control off, and do not turn off Defender or SmartScreen, to get around it. Those protections are hard to switch back on. Wait for a signed release, or [report that it was blocked](reporting-a-bug.md#startup-and-installer-problems) with the exact message.
4. **If your antivirus reports a detection**, do not add an exclusion and do not restore a quarantined file. Report it, quoting the name it shows.

PlayNice's installer never changes Windows security settings, and PlayNice does not ask you to.

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
