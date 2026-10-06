# Amiga 360 Refresh 2026 - Feature Edition

**The controller-first Amiga emulator for Xbox 360 JTAG/RGH systems, refreshed for 2026 and finally taught a few new tricks without making the fifteen-year-old core question its life choices.**

Amiga 360 Refresh 2026 - Feature Edition continues Lantus' Amiga360 port, based on P-UAE 2.3.3. It preserves the fast, direct console experience and adds the missing everyday machinery around it: reliable storage, a practical media library, modern presentation and a GUI designed to work from the sofa.

## Download

Download the complete public Xbox 360 package from the [Feature Edition release](https://github.com/djforrest33-hash/amiga360-refresh-2026-xbox-binaries/releases/tag/v1.0-feature-edition). It is one verified ZIP: extract it to one folder and launch `A360RF26.XEX` on a JTAG/RGH console.


## What is inside

- Native A500, A1200 and A4000-oriented profiles, including WHDLoad and Picasso96 setups.
- Stable Picasso96 modes up to 1024x768.
- ZIP and M3U multidisk support, natural ordering and a 20-slot disk swapper.
- DH0-DH3 hardfile handling, shared `SOFTWARE:` mounting and saved-profile recovery.
- Read-only CD0 ISO mounting, replacement and explicit eject through `uaescsi.device`.
- Savestates with screenshots, favorites, previews and cover art.
- Classic and Dark themes plus a GUI music player.
- A paused-frame GUI with smooth zoom transitions: once emulation has started, every GUI page uses the exact last Amiga frame as its background.
- Compact activity lamps for `SND`, `CPU`, numeric FPS, `DH0`, `CD` and `DF0`-`DF3`.
- Mixed Legacy controls by default, with optional joystick-only and mouse-only modes for the handful of games that believe Fire should also summon Player 2, a mouse click and possibly a small demon.

## Project status

The Xbox edition is feature-closed. Small, reproducible bugs may still be fixed, but the P-UAE 2.3.3 CPU and chipset core will not be rewritten. The work concentrates on the frontend, controller workflow, storage and CD plumbing, integration, reliability and presentation.

Testing covered real Xbox 360 hardware, floppy software, Workbench/HDF systems, WHDLoad, Picasso96, CD0, savestates, input modes and repeated configuration changes. Real-hardware testing is not glamorous; at least three consoles have already volunteered for permanent retirement.

## Legal content is not included

This repository and its public packages contain no Kickstart ROM, Workbench installation, commercial game, user hardfile or music collection. Supply only material you legally own.

The author developed this project for study and personal satisfaction using legally owned Amiga 500 and Amiga 1200 computers, their Kickstart and Workbench media, and 38 legally owned original games. Do not use this emulator, or any part of it, in a distribution containing copyrighted material without the rights holder's authorization.

## Documentation

The binary package includes manuals, compatibility notes, release notes and the changelog. The runtime executable is permanently named `A360RF26.XEX`.

## Credits and license

Core and port lineage: Bernd Schmidt, Toni Wilen, Richard Drummond, Mustafa "GnoStiC" Tufan, Lantus and their contributors. Amiga 360 Refresh 2026 - Feature Edition by Vanni B. Monti-Condesnitt.

The project remains free software under the GNU GPL. Preserve copyright notices and component licenses when redistributing modified builds.

Bug reports and suggestions: `xrest@hotmail.com`

**Buy Me a Coffee if you like the Work - PayPal.Me @VMontiCondesnitt**

