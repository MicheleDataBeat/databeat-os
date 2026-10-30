<a href="https://micheledatabeat.github.io/"><img src="assets/databeat-mark.svg" alt="DataBeat" width="40" height="40"></a>

# DataBeat OS

Musical firmware for the **first-generation Korg volca sample**, by
[DataBeat — Michele Ibba](https://micheledatabeat.github.io/).

Build rhythms that change across eight bars, place hits ahead of or behind the
beat, play samples in a scale, loop part of a bar, and perform with repeats,
vinyl stops, backcues and a frozen loop.

> ## ➜ Install DataBeat OS 1.0 with VolcaStudio XL
>
> **This repository contains documentation only: no firmware, no updater and no
> code.** DataBeat OS is installed with the free companion application
> **[VolcaStudio XL](https://micheledatabeat.github.io/volcastudio-xl-releases/)**,
> which builds it on your computer from Korg's own updater:
>
> 1. **Download VolcaStudio XL** for Windows, macOS or Linux: the Browser App
>    or the Desktop App.
> 2. **Download Korg's official updater.** On Korg's
>    [volca sample download page](https://www.korg.com/us/support/download/software/0/370/1475/),
>    read Korg's licence agreement and download **System Updater 1.42**
>    (`volcasample_updater_1_42.zip`). Keep it unchanged.
> 3. **Add it in Studio's Firmware section.** Studio builds DataBeat OS 1.0,
>    checks the result and keeps Korg 1.42 for returning.
> 4. **Install it.** Connect the computer to the Volca's **SYNC IN**, power on
>    holding **FUNC + PLAY** until **UPdt** appears, follow Studio's guided
>    update and wait for **End**.
>
> Step by step, with checksums: **[Install DataBeat OS](docs/INSTALL.md)**.

At startup the display scrolls **dAtAbEAt OS**.

## Return to Korg firmware

**Hold MEMORY + PLAY while powering on the Volca.** Then select
**Korg volca sample 1.42** in Studio and follow the
[return-to-Korg procedure](docs/RETURN-TO-KORG.md).
Keep a backup of your patterns first. No intermediate firmware or factory
reset is needed.

## What it does

- **Hands-free FUNC.** Press FUNC once and it stays on; press it again to turn
  it off. With FUNC on, SAMPLE/SELECT chooses an extension page and FUNC opens
  it. Edits change the pattern in use at once; **WRITE saves the whole
  pattern** to a memory, as on the standard Volca.
- **Predictability.** Every step of every part chooses which of **eight bars**
  it plays in: ALL plus P.01–P.23, 24 choices.
- **Bar filter.** Silence a part in any of its eight bars, independently.
- **Microtiming, echo and ratchet.** Move single hits by −15…+15 units of
  1/32 step, add up to four diminishing echoes, or play a step as up to four
  strokes.
- **Intra-bar loop.** Repeat a span of steps 1–16 times before the pattern
  continues; set it from its page or from inside the performance page.
- **Musical pitch and slicing.** Sixteen SPEED scales, pitch envelopes of
  ±24 semitones, attack and decay in musical lengths, and sixteen equal sample
  zones.
- **Performance page.** Hold a pad for octave shifts, a master gate, beat
  repeat of the selected part, vinyl stops, backcues or a fading scratch.
  Mute parts and choose patterns without leaving the page.
- **Reverb, lo-fi delay and freeze.** Native reverbs, a mono lo-fi delay, or a
  captured loop at half, normal or double speed, forwards or reversed.
- **Pattern backup.** VolcaStudio XL captures all ten memories and the pattern
  in use through audio, and restores the memories you choose.

The [manual](docs/MANUAL.md) explains every page and control. The
[technical notes](docs/TECHNICAL.md) cover the patching model, hashes, memory
and stack budget, and the pattern format. See the [changelog](CHANGELOG.md).

Volca Sample 2 is not supported. You do not need to install Korg 1.42 first:
Studio only uses Korg's updater file to build DataBeat OS.

## MIDI

DataBeat OS keeps **Korg's original MIDI control and synchronization**. Studio
uses a MIDI request for the audio pattern backup. Control change 49 sets a
part's stored volume, as on the original firmware; the
[manual](docs/MANUAL.md#midi) explains how to restore full volume.

## Credits and rights

Thanks to **Pajen** for his pioneering Volca firmware work (BETA7), which
informed DataBeat OS's research and design. DataBeat OS uses the Korg 1.42
image as its base.
[Pajen BETA7, hosted by Ranzee](https://ranzee.com/volca-sample-unofficial-firmware/).

DataBeat OS is unofficial research and interoperability work, not affiliated
with or endorsed by Korg. **No open-source or redistribution license is
granted.** This repository distributes no Korg firmware and no DataBeat OS
updater. See [credits and rights](THIRD_PARTY.md).

[DataBeat](https://micheledatabeat.github.io/) ·
[VolcaStudio XL](https://micheledatabeat.github.io/volcastudio-xl-releases/)
