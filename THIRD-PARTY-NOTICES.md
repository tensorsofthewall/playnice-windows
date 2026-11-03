# Third-party notices

PlayNice's own code is **proprietary software**. It is not open source, and this repository does not contain it. PlayNice also uses third-party software that has its own licences, listed here. The licence of a third-party component applies to that component only; it does not change the licence of PlayNice's own code, and PlayNice's licence does not change theirs.

## Qt 6.12.0

The PlayNice desktop application uses these Qt libraries: Qt6Core, Qt6Gui, Qt6Network, Qt6Svg and Qt6Widgets, plus Qt's platform, style, image-format, icon-engine, generic, network-information and TLS plug-ins. Qt is copyright The Qt Company Ltd. and other contributors. Qt and the Qt logo are trademarks of The Qt Company Ltd.

**Licence.** These Qt components are used under the **GNU Lesser General Public License version 3 (LGPLv3)**. They are **not** PlayNice's proprietary code. The licence texts and Qt's licensing information are published here:

- GNU LGPL version 3: <https://www.gnu.org/licenses/lgpl-3.0.html>
- GNU GPL version 3, which the LGPL refers to: <https://www.gnu.org/licenses/gpl-3.0.html>
- Qt's licensing information: <https://www.qt.io/licensing/>

**How Qt is used.** The Qt libraries are separate `Qt6*.dll` files and plug-in folders next to `playnice.exe`; they are dynamically linked, not built into PlayNice's own programs.

**Qt source code.** The Qt files in a PlayNice installer are Qt 6.12.0 (the modules qtbase and qtsvg), copied from The Qt Company's kit without change. The `licenses` folder of the installation contains `QT-SOURCE-OFFER.txt`, a written offer to give you the corresponding source code (the two official archives, named there with their SHA-256 values). To ask, open an issue titled "Qt source request" at <https://github.com/tensorsofthewall/playnice-windows/issues/new/choose>. The Qt Company also publishes the archives at <https://download.qt.io/official_releases/qt/6.12/6.12.0/submodules/>.

Qt contains third-party code that has its own licences. The notices for that code are in the installation's `licenses` folder (`QT-THIRD-PARTY-NOTICES.txt`).

## Microsoft Visual C++ Redistributable

The Microsoft Visual C++ Redistributable (x64) is **not** included in the PlayNice installer. It is a prerequisite of the computer. Install it from Microsoft: <https://aka.ms/vs/17/release/vc_redist.x64.exe>.

## VB-CABLE

VB-CABLE is a virtual audio device made by VB-Audio Software (Vincent Burel). Its origin is <https://www.vb-cable.com> (also <https://vb-audio.com/Cable/>). VB-CABLE is donationware: all participations are welcome, and you can support VB-Audio directly at <https://vb-audio.com/Services/licensing.htm>. It is independent of PlayNice and is not developed or owned by PlayNice; VB-Audio's own licence terms apply to it.

PlayNice does **not** include, download, install, start or remove VB-CABLE, and nothing of VB-Audio's is in the PlayNice installer or its `licenses` folder. You get VB-CABLE yourself from VB-Audio (<https://vb-audio.com/Cable/>) and VB-Audio's own terms apply to what you download. PlayNice and its installer only look at whether a VB-CABLE device is present and explain how to install it; the uninstaller never removes it. PlayNice is not made, endorsed or certified by VB-Audio. VB-CABLE and VB-Audio are the property of their owners.
