# DataBeat OS 1.1 — technical notes

For readers who want the details behind the [manual](MANUAL.md). Nothing here
is needed to install or play DataBeat OS. This repository contains no firmware
and no code.

## Patching model

DataBeat OS is Korg's volca sample firmware 1.42 plus the DataBeat extension.
It is distributed as a patch, never as firmware:

1. You download Korg's *volca sample System Updater 1.42* from Korg.
2. VolcaStudio XL decodes the Korg updater WAV to the 128 KiB firmware image and
   checks its SHA-256.
3. Studio applies its pinned patch to that image. The patch is a list of
   operations: **2 900** in total, **2 108** literal blocks with DataBeat OS's
   own bytes (**29 444** bytes) and **792** copies of byte ranges from your Korg
   image.
4. Studio checks the SHA-256 of the result, encodes it as an updater WAV on the
   structure of your Korg updater and checks that WAV's SHA-256 and length too.
   If any check fails, nothing is saved.

The literal data contains no span of 8 or more bytes of Korg's image; every
release build checks this against Korg's updater. The patch and Studio's
other code are not covered by the same licence: see
[credits and rights](../THIRD_PARTY.md).

## Hashes

| What | Bytes | SHA-256 |
| --- | ---: | --- |
| Korg `volcasample_updater_1_42.zip` | | `f0df310b8bd43b6367dbd0c54ba75e3db53942087e1a4b1ae049f8f08e1731f3` |
| Korg `volcasample_sys_0142.wav` | | `8fe4f43c333a753d589a4d7eff7859e8fce7155cf54b889f4848d595721a55a9` |
| Korg 1.42 firmware image | 131 072 | `4ea3647d489210cdbbba3562b48cc2ff2a6a851a00e5564f1247afc15a5f17b4` |
| DataBeat OS 1.1 firmware image | 131 072 | `5d2dd053563bc76b2106f87393984039c44b7d1876dc1846b837a89c1ebc4ef1` |
| DataBeat OS 1.1 updater WAV | 6 798 220 | `b0fa3052173bd9ff192f8f4bc2c3843c6dd407ef7bf991203f92acd75336bf8c` |

The updater WAV is stereo PCM16 at 44.1 kHz, about 38.5 seconds. Its header
carries updater version **1.60**, which the REC version check can show. The
WAV was decoded by an independent decoder and checked on all 512 pages with a
model of the native receiver, CRC/ECC and simulated flash. Firmware images and
updaters are never published: Studio rebuilds them bit for bit.

## Memory and stack budget

| Resource | Used | Available |
| --- | ---: | ---: |
| Extension code and presets | 30 559 B | 52 704 B (22 145 B free) |
| Main stack, conservative worst case | 496 B | 40 B margin |
| Bootstrap reservation (call area, event queue, loop and repeat state) | 352 B | — |
| Event queue | 28 events | — |

The stack figure comes from a static audit of the complete image: 31 109
decoded instructions from 665 entry points, native paths included. Interrupt,
fault and NMI reserves are kept. DataBeat OS
adds no audio buffer. No physical CPU-load measurement on the instrument is
claimed.

## Pattern format

A pattern is always **2 624 bytes** (`0xA40`), the size of a standard volca
sample pattern. It begins with the native signature `PTST` and ends with
`PTED`. Bytes `0xA20`–`0xA23` hold the marker **`LMX6`**, which identifies the
DataBeat OS 1.1 pattern format. The settings that WRITE saves with a pattern,
such as the Predictability choice, the Echo and the Ratchet of each of the 160
part steps, live inside those 2 624 bytes, so a pattern travels through the
standard SYRO transfer and the audio backup unchanged in size.

A pattern in another format does not play, save or take knob edits on
DataBeat OS 1.1, and the firmware does not convert it. VolcaStudio XL 1.2
converts patterns from DataBeat OS 1.0 (marker `LMX3`), from the earlier XL
firmware (`LMX2`) and from the Korg firmware into this format, and writes the
result to a new bank.

## Startup text

At startup the display scrolls **dAtAbEAt OS**. The text is written with the
glyphs of the volca sample's own seven-segment font: eleven glyphs, the space
included, followed by zeros.
The native font's letter O is lower case, so the capital O of OS uses the
font's first glyph, the zero.

## Updater and MIDI

DataBeat OS keeps Korg's updater mechanism: the volca sample receives it through
**SYNC IN** in update mode (**FUNC + PLAY**). Korg's original 1.42 updater is
accepted in forced update mode (**MEMORY + PLAY**); see
[Return to Korg firmware](RETURN-TO-KORG.md). Standard Korg MIDI control and
synchronization are unchanged, except that data bytes arriving before any
status byte are ignored, as MIDI 1.0 asks; Studio uses a MIDI request for the
audio pattern backup.
