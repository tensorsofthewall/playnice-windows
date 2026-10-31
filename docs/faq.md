# Frequently asked questions

## What does PlayNice do?

It plays your computer's sound, or the sound of one program, on several audio outputs at the same time.

## What do I need?

64-bit Windows 11, the PlayNice installer, and the separate VB-CABLE virtual audio device. See [Getting started](getting-started.md).

## Why do I need VB-CABLE?

Windows plays a program's sound on one device. PlayNice needs a virtual playback device, **CABLE Input**, to receive that sound before it sends it to your speakers. VB-CABLE is a separate donationware product from VB-Audio Software (<https://www.vb-cable.com>). The PlayNice installer carries VB-Audio's package, and PlayNice starts VB-Audio's installer when you choose **Install VB-CABLE**; you can also install it yourself from <https://vb-audio.com/Cable/>. VB-Audio's installer asks for administrator permission and Windows must restart afterwards. See [Getting started](getting-started.md#2-install-vb-cable-from-playnice).

## Will speakers be perfectly in step?

No promise is made. Devices differ in how long they take to play sound, and Bluetooth speakers often add noticeable delay. You can set a delay for each speaker by ear. PlayNice does not measure delay automatically.

## Will picture and sound match in a video?

PlayNice does not promise that. If you watch video, sound on a Bluetooth speaker may arrive late compared with the picture, and the player's own audio-delay setting may help. This has not been tested for every player.

## Does it work with every speaker?

No. It works with audio outputs that Windows lists as playback devices, but not every device or every Bluetooth speaker behaves well. See [Troubleshooting](troubleshooting.md) and [report](reporting-a-bug.md) anything you find.

## Does PlayNice change my Windows default audio device?

No. PlayNice never changes your default playback device, and it never changes which device a program uses. You choose what plays to the cable in Windows yourself, usually for one program at a time in the Volume mixer. See [Getting started](getting-started.md#9-start-audio-then-route-one-program-to-the-cable).

## Does closing the PlayNice window stop the audio?

No. PlayNice has a window and a background controller that runs the audio. Closing the window, or quitting it, leaves audio running. Use **Stop audio** to stop it. See the [Settings guide](settings-guide.md#controller-shutdown).

## Why are the volume sliders tied to Windows?

Each speaker's slider and mute button change that device's volume and mute in Windows, so the same volume applies outside PlayNice. They are not saved with a setup, and they work while the setup is playing. See the [Settings guide](settings-guide.md#master-and-per-speaker-windows-volume).

## Does it start with Windows?

Only if you turn on **Start PlayNice at sign-in** in Settings. It is off by default. See the [Settings guide](settings-guide.md#start-at-sign-in).

## Is PlayNice open source?

No. PlayNice is proprietary software. This repository is for downloads, documentation and support, and does not contain the source code.

## Does PlayNice need administrator rights?

Not for the recommended install (**Install for me only**). Only VB-Audio's installer, and its removal tool, ask Windows for administrator permission, and only after you choose **Install VB-CABLE** (or **Remove VB-CABLE** while uninstalling). The VB-Audio driver is signed by VB-Audio and Microsoft; that is separate from PlayNice's own installer, which is currently not signed.

## Does uninstalling PlayNice remove VB-CABLE?

Only if you choose it. After you confirm the uninstall, Setup asks **Also uninstall VB-CABLE?**; **Keep VB-CABLE** is the default, a silent uninstall always keeps it, and other programs may use it. Removing it opens VB-Audio's own setup and needs a restart. See [Installation](installation.md#uninstall).

## Windows warns about the installer. What should I do?

The installer is not yet signed, so Windows may warn about it or block it. Only use an installer from this repository's Releases page, check its checksum, and do not turn off Defender or SmartScreen or add exclusions to run it. See [Installation](installation.md#windows-warnings), and [If Smart App Control blocks PlayNice](installation.md#if-smart-app-control-blocks-playnice) if Smart App Control stops it.

## How do I check one speaker?

Choose **Test** on its row. PlayNice plays a short, soft sound on that speaker only and then says *Test sound sent to ... Did you hear it?* PlayNice can tell that Windows accepted the sound; it cannot know whether you heard it. **Test** works without VB-CABLE carrying anything, does not change the Windows volume or mute, and is off while the playing setup uses that speaker.

## Why do I hear nothing even though PlayNice is playing?

Usually because no program is sending its sound to **CABLE Input**. PlayNice only plays what arrives there. Choose **Open Windows Volume Mixer** on the card under the source, set the program's output to **CABLE Input**, and start something playing. **Can't hear audio?** lists the other causes it can detect. PlayNice never changes the Windows default device or a program's output by itself.

## Does PlayNice send my information anywhere?

PlayNice does not upload your setups, devices or diagnostic reports. A [diagnostic report](diagnostic-report.md) is saved on your computer only when you ask for one, and you decide whether to share it.

## Where do I report a problem or ask for a feature?

[Open an issue](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose). Read [Reporting a problem](reporting-a-bug.md) first. Report security problems privately, as described in the [security policy](../SECURITY.md).
