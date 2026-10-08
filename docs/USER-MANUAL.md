# Amiga 360 Refresh 2026 - Feature Edition User Manual

**Platform:** Xbox 360 JTAG/RGH  
**Release:** Final Xbox Edition

## 1. Installation

Copy the complete runtime directory to Xbox 360 storage. Do not copy only the
XEX: the `media` directory contains the GUI themes and font. Add a legally
obtained Kickstart 3.1 ROM as `Kickstart/kick31.rom` for normal A1200 startup
and Kickstart 1.3 as `Kickstart/kick13.rom` for the A500 profile. Place floppy
images under `Roms`, HDF images under `Hardfiles`, and launch `A360RF26.XEX`.
The historical `Amiga360.xex` name is retired.

No Kickstart, Workbench, game, HDF or music file is distributed with the
project. Empty folders are intentional invitations, not missing downloads.

## 2. Runtime directories

| Directory | Purpose |
|---|---|
| `Cache` | Temporary extracted multidisk images; managed by Amiga360. |
| `Config` | Startup profile, machine profiles and persistent GUI settings. |
| `Config/images` | Preview artwork matching configuration filenames. |
| `Hardfiles` | User-supplied HDF images. |
| `Hardfiles/images` | HDF previews with matching base filenames. |
| `Kickstart` | User-supplied Kickstart ROMs. |
| `media` | Required GUI skins and font. |
| `Music` | Optional MP3/WMA files used only by the GUI player. |
| `Roms` | Floppy images, ZIP sets and M3U playlists. |
| `Roms/images` | Cover previews matching ROM/archive names. |
| `SAVE` | Savestates and their generated BMP previews. |
| `Software` | Host directory mountable in Workbench as `SOFTWARE:`. |

The supplied `Software/Disk.info` gives the `SOFTWARE:` volume its rainbow
A360 Programs icon. Keep the filename exactly as `Disk.info`; Workbench uses
that conventional name for a volume icon.

## 3. Home and GUI navigation

Amiga360 opens on Home before starting emulation. The Home page reports the
active machine and music state and provides access to Disks, Favorites,
Configurations, Hard Disks, Savestates, Music, Options and About.

| Control | GUI action |
|---|---|
| D-pad / left stick | Move focus |
| A | Select or activate |
| B / Back | Previous page; from Home, return to Amiga |
| LB | Context action; on Home, change theme |
| RB | Context action; where shown, reset Amiga |
| R3 | Add/remove favorite, mount Software or refresh music as labelled |
| Start | Return to emulation using the historical shortcut |

Options and Options More are saved when leaving their pages through the
documented controls. Classic and Dark theme choice is persisted and applied at
the next application start.

The two Options pages expose the settings that are useful from a controller:
CPU, chipset, Chip/Fast/Slow/Z3/RTG memory, Picasso96, timing, audio, video and
input mode. A complete `.XAC` also stores media paths, HDF geometry, host state
and low-level compatibility values. Those belong to **Configurations**, the
media browsers or the emulator itself; turning every serialized line into a
checkbox would make the GUI look like an aircraft cockpit designed by a ferret.

On the first launch the GUI uses the selected Classic or Dark artwork. After
emulation starts, LT opens every GUI page over the exact paused Amiga frame,
including Disks, Kickstart, Hard Disks, Options, Savestates and Music. A cool
gradient keeps labels readable, and smooth zoom transitions handle both entry
and return to emulation. The frame is a live pause snapshot, not a screenshot
file, so there is nothing extra to clean up later. Tiny victories count.

## 4. Controller map during emulation

| Xbox control | Amiga360 action |
|---|---|
| Left stick | Original combined mouse/joystick movement; restricted by exclusive mode |
| D-pad | Joystick direction unless Mouse-only mode is selected |
| A | Original combined left-click/fire; restricted by exclusive mode |
| B | Right click unless Joystick-only mode is selected; Enter when no mouse is configured |
| X | Second joystick button unless Mouse-only mode is selected |
| LB + RB | Cycle Mixed Legacy, Joystick Port 2 only and Mouse Port 1 only |
| LT | Open the GUI, once per press |
| Y | Direct Amiga Space key |
| RT | Direct Amiga Enter key |
| Back | Open the virtual keyboard |
| L3 / R3 | Previous/next swapper disk into DF0 |
| Start | F10 while held, then Print Screen on release for common WHDLoad exit-key setups |

Joy+Mouse starts in **Mixed Legacy** mode, preserving the original Refresh 1.0
behaviour used by games whose trainer or intro needs the mouse before joystick
play begins. If a game exposes the shared Amiga mouse/fire lines, press LB+RB
to select **Joystick Port 2 only**. A third press selects **Mouse Port 1 only**
for Workbench or mouse-driven software, and the next press returns to Mixed.
The same three choices are available under **Options > More Options > Input**.
An on-screen status message confirms changes made with LB+RB.

In Joy+Joy mode, controller 1 drives Amiga joystick port 2 (Player 1) and
controller 2 drives port 1 (Player 2). Both use D-pad/left stick, A and X.
Global GUI, keyboard and swapper commands remain reserved for controller 1.

## 5. Floppy images and the disk swapper

The browser recognizes ADF, ADZ, DMS, FDI, compatible IPF, ZIP and M3U.
Amiga360 exposes DF0-DF3 and keeps up to 20 images in the swapper.

- The first four images populate DF0-DF3.
- R3 advances through the complete set and mounts the selection in DF0.
- L3 moves backward.
- The on-screen message identifies drive, position, total and filename.

ZIP members are sorted naturally using Disk, Disc, Side and Part labels, so
Disk 2 precedes Disk 10. M3U order is authoritative and can combine separate
images and ZIP archives. Relative Xbox paths, comments beginning with `#`,
quotes and UTF-8 BOM are accepted.

Use FATX-safe filenames: letters, digits, spaces, hyphens, underscores and
parentheses are the least troublesome choices. A comma may be emotionally
important to a title, but the game itself will not notice its absence.

## 6. Favorites and previews

In Disks, highlight an item and press R3 or activate **Add Favorite**. The
exact filename is saved in `Config/favorites.txt`; rename the file and the
favorite must be added again.

Preview lookup removes the media extension and tries JPEG, PNG and BMP under
the relevant `images` directory. For multidisk names, a common title before
Disk/Disc markers is also tried. Recommended covers are 320x240 or 400x300.
Loading is delayed until navigation settles, keeping large USB libraries
responsive.

## 7. Machine profiles and video

`Config/default.XAC` is the hidden normal startup: 68020/AGA, 2 MB Chip RAM,
8 MB Fast RAM, Kickstart 3.1, no RTG and no automatically mounted HDF. In other
words, Amiga 360 Refresh now starts as the useful A1200 it was meant to become.
The Options pages save changes back to this startup file. The GUI shows exactly
four supported public profiles:

- **A500:** 68000, OCS, 1 MB Chip RAM, accurate timing and no RTG.
- **A1200 RTG:** 68020, AGA, 2 MB Chip, 32 MB Z3 and 16 MB Picasso96.
- **A1200 WHDLoad:** 68020, AGA, 8 MB Fast, an `A1200-WHDLoad.hdf` DH0
  placeholder and the runtime Software folder mounted as DH1/SOFTWARE:.
- **A4000 WHDLoad:** maximum-performance 68040/FPU profile with 32 MB Z3,
  16 MB Picasso96, an `A4000-WHDLoad.hdf` DH0 placeholder and Software as DH1.

Kickstart and HDF paths are placeholders for files you legally provide. The
WHDLoad profiles do not contain WHDLoad games or copyrighted system images.
The Xbox read-only CD0 bridge remains resident in every profile, including
A500. This only exposes `uaescsi.device`; it does not enable RTG, networking,
extra RAM or an emulated physical SCSI controller.

Picasso96 800x600, native 1024x768 and 1280x720 are validated on real hardware,
including Workbench and AmigaOS 3.9 installations supplied by the user. Guest
4:3 modes are presented fullscreen by the Xbox backend; guest icon geometry
remains correct. For Workbench backgrounds, compatible GIF files are the
reliable 1.0 choice. Host-side GUI JPEG previews are unaffected by this guest
datatype limitation.

With **Show LEDs** enabled, the compact strip reads `SND | CPU | FPS | DH0 |
CD | DF0 | DF1 | DF2 | DF3`. Labels are drawn inside the original lamps. HD
keeps blue read/red write activity and floppy drives keep green activity/red
write; CD, sound and CPU workload use distinct colours. FPS remains the live
numeric readout. The old Power lamp was decorative and has been removed.
**Show LEDs on RTG** draws this same strip on Picasso96 screens: this core has
no separate RTG activity source, so there is deliberately no pretend RTG lamp.

## 8. Hardfiles, the Software share and CD0

Use Hard Disks to assign HDF units to DH0, DH1, DH2 or DH3. The selected letter
is stored as the device identity, so removing DH1 does not rename DH2 or DH3.
For an RDB image, the selected letter is used for its first partition and extra
partitions receive deterministic suffixes. DH0 is the intended boot hardfile;
the other letters are forced to non-bootable priority. Profiles reference
example filenames but do not include the corresponding copyrighted systems.
Use **Reset Amiga** after changing HDF or Software assignments so Workbench is
rebuilt with the new device set.

Saved configurations retain complete HDF paths for every DH slot. Older XAC
files containing only names such as `WHD_Games.hdf` are expanded through
`xbox360.hardfile_path` when loaded, so a correct label corresponds to an HDF
that was actually opened.

In Hard Disks, choose any DH0-DH3 letter and press the labelled R3 action to
mount or move the runtime `Software` directory there. Empty intermediate letters
are allowed, and an occupied destination is deliberately replaced. Workbench
sees the directory as volume `SOFTWARE:`. `Config/software-folder.cfg` accepts
a path relative to `GAME:` or an absolute Xbox device path such as
`USB0:\Amiga\Software`; an invalid configured path falls back to
`GAME:\Software`.

ISO images may be selected from Hard Disks and mounted as one read-only CD0
drive by pressing L3 or activating **MOUNT CD0**. If a disc is already mounted,
the same action performs the delayed eject/insert cycle and replaces it with
the selected ISO. Press L3 again on the currently mounted ISO, press L3 while a
non-ISO row is selected, or select an ISO and activate **Unmount Image**, to
eject it and leave CD0 empty. Allow a few seconds for Workbench to receive the
media-change notification. CD0 does not create a DH unit or make the image
bootable.
Workbench installations that do not already
have a CD0 mountlist can use `Software/Amiga360-CD0-Setup`; read its README,
run `Install-CD0` once, then reboot Workbench. The supplied mountlist uses
`uaescsi.device` with UNIT=0 and requires a compatible `L:cdrom-handler`
installed from media you legally own; no third-party filesystem binary is
distributed.

If an older installation reports **uaescsi.device not found**, first boot it
with this corrected XEX and reset the Amiga once. If you prefer to remove CD0,
copy the setup folder to a writable Amiga disk and run `Execute Remove-CD0`.
That command works without the original backup and leaves `L:cdrom-handler`
untouched for other CD configurations.

### ClassicWB iGame with AGS metadata

The final release supplies `Software/iGame-A360-Classic` and the same package
on the Workbench Tools ISO. It uses the compact ClassicWB iGame executable,
without the AGS launcher, ButtonMenu scripts or startup layer. The AGS catalogue
has been converted into ClassicWB's native format: 3,937 game paths and 133
detailed genres. The 133 beta/demo rows mixed into AGS's games CSV are excluded.
The exact source CSV remains under `CSV-Reference`; the classic executable does
not read it directly. The custom Amiga 360 splash is included as `igame.iff`.

On the CD, run **INSTALL-CLASSICWB-IGAME**. It always reads from the
`AMIGA360_TOOLS:` volume and writes to `SYS:Programs/iGame-A360-Classic`; do
not start iGame directly from the read-only CD. Run `SETUP-A-GAMES-ASSIGN`, or
add these commands to `S:User-Startup`:

```text
Assign A-Games: "DH2:Games-1/games"
Assign A-Games: "DH2:Games-2/games" ADD
```

All stored catalogue paths begin with `A-Games:`. The preference and script
files use Amiga-safe LF endings, so no hidden carriage-return character is
appended to the repository path. The converted catalogue needs no scan. To
build a list containing only locally present games, run `RESET-FOR-OWN-SCAN`
first and scan once. `USE-A-GAMES-CATALOGUE` restores the supplied catalogue
without reinstalling.

## 9. Savestates

Savestates live in `SAVE`. Saving creates `Name.SAV` and a matching 320x240
BMP preview. Deleting a state removes both. Loading restores the emulation and
realigns the multidisk swapper with the image actually present in DF0.

Use the same machine profile, Kickstart and disk set used to create the state.
Savestates are snapshots, not tiny time machines with universal compatibility.

## 10. Music player

The GUI player supports MP3 and WMA, alphabetical browsing, random playback,
previous/next, play/pause, stop, repeat, volume and an explicit R3 **Refresh
Folder** action. Music state and volume are persisted.

The player and playlist exist only while the GUI owns the screen. They are
released before entering emulation so the Amiga core keeps priority and USB
storage is not scanned continuously.

## 11. Troubleshooting

- **No boot screen:** verify `Kickstart/kick.rom` and the selected profile.
- **HDF does not boot:** mount it as DH0 and verify geometry/profile settings.
- **SOFTWARE: missing:** confirm the host folder exists and remount it from
  Hard Disks.
- **uaescsi.device not found:** use the corrected XEX, reset once, and verify
  the selected configuration has not been replaced by an older custom build.
  To disable CD0, run `Execute Remove-CD0` from the setup folder and reboot.
- **Preview missing:** match the base filename exactly and use a small image.
- **ZIP copy fails:** sanitize the outer FATX filename before transfer.
- **Savestate behaves incorrectly:** restart with the original profile/media.
- **Workbench background stays grey:** use a tested compatible GIF and reload
  the guest screen; JPEG/PNG guest decoding is a known historical limitation.

## 12. Reporting a problem

Follow [PUBLIC-TESTING.md](PUBLIC-TESTING.md). Include hardware, storage,
profile, XEX hash, exact reproduction steps and repetition rate. Never attach
commercial ROMs or personal hardfiles to a public report.

Bug reports and suggestions are also welcome at `xrest@hotmail.com`.

## 13. Final Xbox scope

This Xbox release is feature-closed. Small reproducible bugs may still be fixed,
but the emulator core will not be rewritten. The PC edition remains free to
become the experimental joypad-first monster lab. Please feed it responsibly.

## 14. Author, intent and legal use

Vanni B. Monti-Condesnitt developed Amiga360 Refresh for study and personal
satisfaction using legally owned Amiga 500 and Amiga 1200 computers, their
Kickstart and Workbench media, and 38 legally owned original games.

The CPU/chipset emulation core was deliberately left unchanged. Reworking a
roughly 15-year-old core would have been a heroic waste of time; the goal was
to enrich a project that, with earlier and stronger support, might have become
a milestone. Development was equal parts fun and swearing at the screen. The
old core has even run Workbench 3.9 in Picasso mode smoothly in the author's
tests, so it clearly still knows a few tricks.

The author explicitly forbids using this emulator, or any part of it, in
another project or distribution that includes copyrighted material without
the rights holder's authorization. This release contains no Kickstart,
Workbench, commercial game, HDF or other proprietary Amiga content.

**Buy Me a Coffee if you like the Work - PayPal.Me @VMontiCondesnitt**
