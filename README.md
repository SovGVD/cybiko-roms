# Cybiko ROMs and software, kept safe

A backup of the Cybiko Xtreme and Cybiko Classic firmware dumps and original software, collected
because most links to them are dead. They are what
[Dragonfruit](https://github.com/SovGVD/Dragonfruit-JC4827W543-esp32)'s
Cybiko emulator and the [web emulator](https://github.com/SovGVD/cybiko-web-emulator)
run. Everything here is Cybiko, Inc.'s work (the company closed in 2003), kept
for preservation. Checksums of every file are in [SHA1SUMS](SHA1SUMS).

## What is here

| Folder | What | Use it for |
| --- | --- | --- |
| `xtreme/` | `cyrom150.bin` (32 KB boot ROM) and `cyos_v1508.bin` (512 KB flash, CyOS 1.5.08), the same files as in MAME's `cybikov1` set | the two files every emulator needs |
| `classic/` | `cyrom112.bin` (32 KB boot ROM) and `flash_v1246.bin` (528 KB DataFlash, CyOS 1.2.46) of the first Cybiko, the Classic: MAME's `cybikov1` dumps, as [ReBiko](https://github.com/RetroCodeRamen/rebiko)'s release ships them (`roms/boot.bin`, `roms/flash.bin`) | the Classic in either emulator |
| `cyos-updates/` | `ccyphRU1.5.08r.boot`: Russian CyOS 1.5.08. `avr50c6f.boot`: firmware for the radio's AVR co-processor | an optional CyOS update; the emulators skip the AVR file |
| `mp3-cartridge/` | from the MP3 player cartridge's CD: `MP3.cap` (the cartridge software) and `Update_US.csu` (CyOS 1.5.06 and apps). The CD's music video clips are only in the CD image | the MP3 cartridge |
| `xtreme-cd/` | the apps, games and installers (`.cap`) from the Xtreme Installation CD | adding apps and games |
| `cd/` | both CDs, whole: `Cybiko Xtreme Installation CD.img` (raw MODE2/2352 sectors) and `Cybiko Xtreme MP3 Installation Disc.iso` | everything else: EZ Loader, the Converter, manuals |

**Two `MP3.cap` files.** The one on the Xtreme Installation CD
(`xtreme-cd/MP3.cap`, `sdflash.dl` 21.1.3) is older: it stops after reading
the card's size and never shows the card. Use the one from the cartridge's own
CD, `mp3-cartridge/MP3.cap` (`sdflash.dl` 21.1.4, `MP3Player.dl` 24.2.1).

## Using them

- **Web emulator:** pick `xtreme/cyrom150.bin` and `xtreme/cyos_v1508.bin` on
  the first screen. Add `.app`, `.cap` and `.csu` files with "Add files to the
  Cybiko" (installers are unpacked by the page). For the MP3 cartridge, add
  `mp3-cartridge/MP3.cap` the same way, then put MP3s on the card in
  Settings.
- **Dragonfruit board:** see its
  [docs/cybiko.md](https://github.com/SovGVD/Dragonfruit-JC4827W543-esp32/blob/main/docs/cybiko.md):
  the two dumps go in `/Cybiko` on the SD card, apps in `/Cybiko/apps`, card
  files in `/Cybiko/card`, a `.boot` update in `/Cybiko`. The Classic's two
  files go in `/Cybiko/Classic`.
- **Cybiko Classic:** in the web emulator make a new device with the model
  Cybiko Classic and press Start; it fetches the two files from `classic/`.
- **Formats and tools** (unpacking `.cap`, MXD clips, and so on):
  [cybiko-docs](https://github.com/SovGVD/cybiko-docs).

## Where they came from

The dumps match MAME's `cybikov1` set. The Classic's were taken from the
release zip of [ReBiko](https://github.com/RetroCodeRamen/rebiko) by Dan
Berkowitz (v1.1027.1b), whose `boot.bin` and `flash.bin` are the same files
(same SHA-1) as MAME's `cyrom112.bin` and `flash_v1246.bin`. The Xtreme Installation CD is also on
the [Internet Archive](https://archive.org/details/CybikoXtremeInstallationCD)
and the [cybiko.net mirror](https://mirror.jcx.life/cybiko/CD/). We found
no other public copy of the MP3 cartridge CD or the Russian CyOS.
