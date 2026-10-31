# Third-party notices

PlayNice's own code is **proprietary software**. It is not open source, and this repository does not contain it. PlayNice also uses third-party software that has its own licences, listed here. The licence of a third-party component applies to that component only; it does not change the licence of PlayNice's own code, and PlayNice's licence does not change theirs.

## Qt 6.12.0

The PlayNice desktop application uses these Qt libraries: Qt6Core, Qt6Gui, Qt6Network, Qt6Svg and Qt6Widgets, plus Qt's platform, style, image-format, icon-engine, generic, network-information and TLS plug-ins. Qt is copyright The Qt Company Ltd. and other contributors. Qt and the Qt logo are trademarks of The Qt Company Ltd.

**Licence.** These Qt components are used under the **GNU Lesser General Public License version 3 (LGPLv3)**. They are **not** PlayNice's proprietary code. The licence texts and Qt's licensing information are published here:

- GNU LGPL version 3: <https://www.gnu.org/licenses/lgpl-3.0.html>
- GNU GPL version 3, which the LGPL refers to: <https://www.gnu.org/licenses/gpl-3.0.html>
- Qt's licensing information: <https://www.qt.io/licensing/>

**How Qt is used.** The Qt libraries are separate `Qt6*.dll` files and plug-in folders next to `playnice.exe`; they are dynamically linked, not built into PlayNice's own programs.

**Qt source code.** The Qt Company publishes the source code of Qt releases at <https://download.qt.io/official_releases/qt/>.

Qt contains third-party code that has its own licences. See Qt's own documentation of the licences used in Qt for details.

## Microsoft Visual C++ Redistributable

The Microsoft Visual C++ Redistributable (x64) is **not** included in the PlayNice installer. It is a prerequisite of the computer. Install it from Microsoft: <https://aka.ms/vs/17/release/vc_redist.x64.exe>.

## VB-CABLE

VB-CABLE is a virtual audio device made and licensed by VB-Audio. It is **not** included in or installed by PlayNice. PlayNice can use it when you install it yourself from <https://vb-audio.com/Cable/>. VB-CABLE and VB-Audio are the property of their owners.
