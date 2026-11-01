# Drum machine samples

One folder per kit, one 16-bit mono WAV per voice (`kick.wav`, `snare.wav`, …), made by
`npm run samples -- <folder> [<folder> …]` (`scripts/make-samples.mjs`) from

- the kits of the archive.org item
  ["drum machine samples"](https://archive.org/details/drum-machines-collection), one zip per
  machine, unzipped, and
- the [Salamander Drumkit](https://archive.org/details/SalamanderDrumkit) by Alexander Holm (its
  `OH/` folder of overhead recordings, in `salamander/OH`).

The script mixes each sound to mono, trims it where it has died away (60 dB under its peak) or at
a length limit (the acoustic kit's long cymbal and tom tails), fades the end and normalises it to
−1 dBFS. Which voices a kit lacks, and what stands in for them, is in `src/machines.ts`.

| Folder      | Kit                      | Taken from                                               |
| ----------- | ------------------------ | -------------------------------------------------------- |
| `kr55/`     | `Korg KR55.zip`          | Kick, Snare, Rim, Chat (closed hat), Hat (open hat), Cymb (ride and crash), Tom, Conga, Cowb, Clav |
| `tr808/`    | `Roland TR808.zip`       | Kick05, Snare01, Rim01, Clap01, Hat_C01, Hat_O03, Ride03 (ride), Ride01 (crash), Tom01–03, Conga04, Conga02, Cow, Clave, Shaker02 |
| `lm1/`      | `Linn LM-1.zip`          | Kick1, SnareDrum1, Sst (rim), Clap, Chh, Ohh, Ride, Crash, Lotom, Midtom, Hitom, Congal, Conga, Cowb, Cabasa |
| `dmx/`      | `Oberheim DMX.zip`       | Kick01, Snare01, Rim, Clap, Hat_C, Hat_O, Ride, Crash, TomLo, TomMid, TomHi, TimbaleLo, TimbaleHi (congas), Cabasa |
| `linndrum/` | `Linn Linndrum.zip`      | Kick, SnareDrum, Sst (rim), Clap, Chh, Ohh, Ride, Crash, Toml, Tom, Tomh, Congal, Congah, Cowb, Cabasa |
| `tr909/`    | `Roland TR-909.zip`      | Set3: Bd05, Sn01, Rs01, Clp01, Ch01, Oh10, Ride01, Lt01, Mt01, Ht01; Set2: CRASH1 |
| `tr707/`    | `Roland TR707.zip`       | Bd1, Sd0, Rim, Hcp, HH_c, HH_o, Rid, Crs, Lt, Mt, Ht, Cow, Tam (shaker) |
| `sp1200/`   | `EMU SP1200.zip`         | Snare1, Rim, Finger (clap), Clhh1, Ophh1, Ride1, Cymb (crash), Tom2, Tom1, Conga1, Conga3, Cowbell1, Clave1, Cabasa1; the kick from `EMU SP-12.zip` (31.wav) |
| `acoustic/` | Salamander Drumkit, `OH/` | kick_OH_F_1, snare_OH_F_1, snareStick_OH_F_1 (rim), snare2_OH_MP_1 (clap: the second snare), hihatClosed_OH_F_1, hihatOpen_OH_F_1, ride1_OH_MP_1, crash1_OH_FF_1, loTom_OH_MP_1, hiTom_OH_F_1, cowbell_MP_1, hihatClosed_OH_P_1 (shaker) |

The SP-1200 kit's own kicks (`Kick1`, `Kick2`) are clicks: their body sits at about 150 Hz and
they stop after 0.13 s. The kick of its predecessor, the SP-12 (the same 12-bit sound), stands in.

**Rights.** The acoustic kit is the Salamander Drumkit by Alexander Holm, licensed
[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/): the files in `acoustic/` are a
modified selection (mono, shortened, faded, normalised) and are shared under the same licence,
with this credit (also in the manual's Credits). The archive.org drum machine collection states no
licence; it was uploaded to the community "opensource_audio" collection without one. The TR-909
kit's Set1 carries its own terms (Rob Roy Recordings, 1995: free to copy, not to be changed, split
up or sold), which is why none of its sounds are used. Check that the drum machine samples may be
published before deploying.
