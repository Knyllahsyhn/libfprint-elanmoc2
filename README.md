> [!NOTE]
> **Unofficial fork.** This repository is current upstream libfprint with
> the experimental `elanmoc2` driver for ELAN Match-on-Chip sensors
> (04f3:0c4c and related) from Davide Depau's branch in
> [libfprint MR !330](https://gitlab.freedesktop.org/libfprint/libfprint/-/merge_requests/330).
> It is not part of the official libfprint release.
>
> **Changes compared to that branch**
>
> - Based on upstream master instead of libfprint 1.94.9.
> - Identify and enroll wait for a finger without timeout. With the fixed
>   10 s timeout, verify ended with `transfer timed out` and the KDE lock
>   screen dropped fingerprint unlock.
> - The libfprint core is unchanged. The MR branch modified storage
>   handling in the core for all drivers; the driver now sets the
>   `STORAGE` feature itself.
> - The outdated elanmoc2 umockdev test is not registered, so the rest of
>   the test suite passes.
> - Arch Linux PKGBUILD in [`packaging/arch/`](packaging/arch/). Build and
>   install with `makepkg -si`. It replaces `libfprint` and
>   `libfprint-elanmoc2-git`.
>
> The branch is rebased onto upstream releases. New commits on the MR
> branch are cherry-picked. Do not run `sync-udev-hwdb`: it pulls the
> unsupported device list from the upstream wiki, which still lists the
> elanmoc2 devices. Driver bugs unrelated to these changes belong in
> MR !330. Once the driver is merged into libfprint, this fork will be
> archived.



<div align="center">

# LibFPrint

*LibFPrint is part of the **[FPrint][Website]** project.*

<br/>

[![Button Website]][Website]
[![Button Documentation]][Documentation]

[![Button Supported]][Supported]
[![Button Unsupported]][Unsupported]

[![Button Contribute]][Contribute]
[![Button Contributors]][Contributors]

</div>

## History

**LibFPrint** was originally developed as part of an
academic project at the **[University Of Manchester]**.

It aimed to hide the differences between consumer
fingerprint scanners and provide a single uniform
API to application developers.

## Goal

The ultimate goal of the **FPrint** project is to make
fingerprint scanners widely and easily usable under
common Linux environments.

## License

`Section 6` of the license states that for compiled works that use
this library, such works must include **LibFPrint** copyright notices
alongside the copyright notices for the other parts of the work.

**LibFPrint** includes code from **NIST's** **[NBIS]** software distribution.

We include **Bozorth3** from the **[US Export Controlled]**
distribution, which we have determined to be fine
being shipped in an open source project.

## Get in *touch*

 - [IRC] - `#fprint` @ `irc.oftc.net`
 - [Matrix] - `#fprint:matrix.org` bridged to the IRC channel
 - [MailingList] - low traffic, not much used these days

<br/>

<div align="right">

[![Badge License]][License]

</div>


<!----------------------------------------------------------------------------->

[Documentation]: https://fprint.freedesktop.org/libfprint-dev/
[Contributors]: https://gitlab.freedesktop.org/libfprint/libfprint/-/graphs/master
[Unsupported]: https://gitlab.freedesktop.org/libfprint/wiki/-/wikis/Unsupported-Devices
[Supported]: https://fprint.freedesktop.org/supported-devices.html
[Website]: https://fprint.freedesktop.org/
[MailingList]: https://lists.freedesktop.org/mailman/listinfo/fprint
[IRC]: ircs://irc.oftc.net:6697/#fprint
[Matrix]: https://matrix.to/#/#fprint:matrix.org

[Contribute]: ./HACKING.md
[License]: ./COPYING

[University Of Manchester]: https://www.manchester.ac.uk/
[US Export Controlled]: https://fprint.freedesktop.org/us-export-control.html
[NBIS]: http://fingerprint.nist.gov/NBIS/index.html


<!---------------------------------[ Badges ]---------------------------------->

[Badge License]: https://img.shields.io/badge/License-LGPL2.1-015d93.svg?style=for-the-badge&labelColor=blue


<!---------------------------------[ Buttons ]--------------------------------->

[Button Documentation]: https://img.shields.io/badge/Documentation-04ACE6?style=for-the-badge&logoColor=white&logo=BookStack
[Button Contributors]: https://img.shields.io/badge/Contributors-FF4F8B?style=for-the-badge&logoColor=white&logo=ActiGraph
[Button Unsupported]: https://img.shields.io/badge/Unsupported_Devices-EF2D5E?style=for-the-badge&logoColor=white&logo=AdBlock
[Button Contribute]: https://img.shields.io/badge/Contribute-66459B?style=for-the-badge&logoColor=white&logo=Git
[Button Supported]: https://img.shields.io/badge/Supported_Devices-428813?style=for-the-badge&logoColor=white&logo=AdGuard
[Button Website]: https://img.shields.io/badge/Homepage-3B80AE?style=for-the-badge&logoColor=white&logo=freedesktopDotOrg
