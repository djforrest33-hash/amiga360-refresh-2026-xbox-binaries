# Amiga 360 Refresh 2026 — Feature Edition

![Xbox 360](https://img.shields.io/badge/Xbox_360-JTAG_%2F_RGH-107C10?logo=xbox&logoColor=white)
![Release](https://img.shields.io/badge/release-1.0_Feature_Edition-6d28d9)
![Interface](https://img.shields.io/badge/interface-controller_first-00b7c3)

![Amiga 360 Refresh GUI](https://cf.preview.redd.it/release-amiga-360-refresh-2026-feature-edition-release-v0-f3nflv2jxsth1.png?width=1080&crop=smart&auto=webp&s=4939cee0673300985cd238bf2d0250207414fbae)

**Amiga 360 Refresh 2026** brings the old Amiga360/P-UAE Xbox 360 port back to life as a controller-first Amiga environment for real JTAG/RGH hardware. It keeps the historical emulation core, rebuilds the frontend around practical daily use, and adds the storage, CD, profile and input work needed to make the emulator feel at home on a console.

This is a separate community project built from the Amiga360 lineage. It does not replace Lantus' original release; it is what happened when somebody looked at a fifteen-year-old emulator and said, “one small refresh should be easy.”

## What the Refresh actually refreshes

This is considerably more than a new skin and a heroic version string. The Refresh adds:

- validated Workbench and AmigaOS 3.9 operation, including Picasso96 modes up to 1024×768;
- curated A500, A1200, A1200 WHDLoad and fast A4000 profiles with persistent machine, video and GUI options;
- an Xbox-pad virtual keyboard plus direct Amiga bindings for Space, F10, Print Screen and the configured WHDLoad exit key;
- correctly separated fire and mouse-button mappings, configurable autofire and two-controller Joy+Joy support;
- three selectable controller modes: Mixed Legacy, Joystick Port 2 and Mouse Port 1, so games, trainers and Workbench stop fighting over the same button;
- reliable ADF, ADZ, DMS, FDI, compatible IPF, ZIP and M3U handling, four floppy drives and a naturally sorted 20-slot disk swapper controlled with L3/R3;
- deterministic DH0–DH3 hardfile reconstruction, safer DH0 boot handling, saved-profile recovery and shared `Software` directory mounting;
- read-only CD0 ISO support through the resident `uaescsi.device` bridge, plus a separate optional tools disc;
- configuration and HDF previews, media artwork, favourites and cached library navigation for large USB collections;
- savestates with screenshots, paired cleanup and restoration of the active multidisk position;
- a Classic/Dark themed GUI, persistent settings and a GUI-only MP3/WMA player with volume, shuffle and library refresh;
- the paused Amiga frame behind every GUI page after emulation starts, with smooth entry and exit transitions;
- labelled activity lamps for CPU workload, live FPS, sound, DH0, CD and DF0–DF3;
- repeated-reset, GUI-return and HDF-startup fixes tested on real Xbox 360 hardware.

The historical P-UAE core remains the historical core. Everything around it received the months-long treatment required to make a fifteen-year-old port behave like a console application instead of an archaeological discovery with a joypad attached.

## Install

1. Download the Xbox binary ZIP from the **Releases** page.
2. Extract the whole package to one folder on an Xbox 360 with JTAG/RGH homebrew support.
3. Launch `A360RF26.xex`.
4. Add only Kickstart, Workbench, game and hardfile media that you legally own.

On real hardware, a Workbench hardfile can occasionally miss its first boot while the backend is settling. Use **Reset Amiga** and restart the emulation session; do not restart the whole application. In testing, the second attempt has been considerably less philosophical.

## Optional Tools CD

`Amiga360-Tools-CD.iso` is published beside the ZIP as a **separate release asset**. It is not inserted into, and does not change, the official binary package.

Mount it from the GUI ISO/CD selector. It provides:

- CD0 install, repair and restore scripts;
- iGame Classic, catalogue and CSV reference files;
- archive and filesystem utilities;
- Amiga 360 wallpapers and documentation.

The normal package already includes the CD0 setup under `Software/Amiga360-CD0-Setup`, including `cdrom-handler`. `uaescsi.device` itself is supplied by the emulator at runtime. The ISO is a convenient toolbox, not a secret second operating system.

**Tools CD SHA-256:** `BAFD560BDB5768A31C0AC30DF99EA48657E62E9073E0E7A9B2B490E1982C3416`

## Screens, discussion and community

- [Main release discussion on Reddit / r/360hacks](https://www.reddit.com/r/360hacks/comments/1wyz179/release_amiga_360_refresh_2026_feature_edition/)
- [Release thread on GBAtemp](https://gbatemp.net/threads/amiga-360-refresh-2026-released-for-xbox-360-and-pc.685040/)
- [ConsoleMods Xbox 360 emulator reference](https://consolemods.org/wiki/Xbox_360%3AEmulators) — useful general context for JTAG/RGH emulator setup; no affiliation or endorsement is implied.

![Amiga 360 Refresh interface](https://cf.preview.redd.it/release-amiga-360-refresh-2026-feature-edition-release-v0-tap4iw2jxsth1.png?width=1080&crop=smart&auto=webp&s=d3d74a10f02749bdee4b505f492098fea6f6896c)

## Project boundaries

No Kickstart ROM, Workbench installation, commercial game, HDF collection or copyrighted music collection is included. The project was developed for study and personal satisfaction using legally owned Amiga 500 and Amiga 1200 systems, their Kickstart and Workbench media, and 38 original games.

Do not use this emulator, or any part of it, in a distribution containing copyrighted material without the rights holder's authorization. Small reproducible bugs can be fixed; a full rewrite of the historical core is outside the Xbox release scope. The fact that it runs Workbench 3.9 in Picasso mode is already the core showing off.

## Credits and contact

Core and port lineage: Bernd Schmidt, Toni Wilen, Richard Drummond, Mustafa “GnoStiC” Tufan, Lantus and their contributors. Refresh engineering by Vanni B. Monti-Condesnitt.

Bug reports, mirror notices and source-access requests: `xrest@hotmail.com`

If the project saved you an evening, the optional coffee link is in the packaged README. Caffeine is still not an emulated chipset.
