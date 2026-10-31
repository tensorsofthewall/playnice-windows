# Security policy

## Report a vulnerability privately

Please do not report security problems in public issues, discussions or comments.

Use GitHub's private reporting: open the [Security tab](https://github.com/tensorsofthewall/playnice-windows/security) of this repository and choose **Report a vulnerability**, or go directly to <https://github.com/tensorsofthewall/playnice-windows/security/advisories/new>. A private report is not shown publicly. It can be seen by you and by people who have been given access to this repository's security advisories, and GitHub, as the host, can also access it. If the **Report a vulnerability** option is not offered, do not post the details in a public issue, discussion or comment; try again later.

Please include:

- The PlayNice version and your Windows version. The version is shown by **About PlayNice** in the **...** menu. If PlayNice will not open, see [Reporting a problem](docs/reporting-a-bug.md#find-your-playnice-version) for other ways to find it, or say that you cannot open it.
- What you found and why it matters.
- Steps to reproduce it, if you can.

Do not include passwords, personal data or anything you are not allowed to share.

## What to expect

This is a small project run by one maintainer. There is no guaranteed response time. Reports are read and answered as soon as the maintainer is able to.

## Supported versions

PlayNice v0.1.0-beta.1 is supported. Only the latest release is supported. PlayNice is in early testing, and fixes are published as new releases, not as patches to older ones.

## Not security reports

Audio problems, crashes that do not involve a security impact, and feature requests belong in [issues](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose).

## Downloads

Download PlayNice only from this repository's [Releases page](https://github.com/tensorsofthewall/playnice-windows/releases). A release page lists the installer's SHA-256 checksum, which tells you the file was not damaged or changed after it was published; it does not by itself show that a file is safe. The installers are not yet signed, so Windows may warn about them or block them (see [Windows warnings](docs/installation.md#windows-warnings)).

If Windows or your security software reports a problem with a PlayNice download, do not turn off Windows Security, Microsoft Defender, SmartScreen, Smart App Control or any other protection, and do not add an exclusion or restore a quarantined file to run it. If you think a file may have been tampered with, or the detection may be real, use the private reporting above. For an ordinary warning about the unsigned installer, you can [open an issue](https://github.com/tensorsofthewall/playnice-windows/issues/new/choose) with the exact message.
