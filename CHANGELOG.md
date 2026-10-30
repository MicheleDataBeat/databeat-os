# Changelog

DataBeat OS is installed with
[VolcaStudio XL](https://micheledatabeat.github.io/volcastudio-xl-releases/),
which builds it from Korg's own volca sample System Updater 1.42.

## 1.0 — 29 October 2026

First release of DataBeat OS for the first-generation Korg volca sample, tested
on the instrument.

- Hands-free FUNC and a page menu: PErF, PrEd, bar filter, rb.ty, tIME, ECho,
  rAtC, LooP and SCAL. Edits change the pattern in use; WRITE saves the whole
  pattern, also with FUNC on or inside a page.
- Predictability with 24 choices (ALL, P.01–P.23) over eight bars, for every
  step of every part; bar filter with eight independent bars per part.
- Microtiming (−15…+15 units of 1/32 step), echo (up to four diminishing
  hits, eight spacings) and ratchet (up to four strokes).
- Intra-bar loop with 1–16 passes, also set from the performance page.
- Sixteen SPEED scales, ±24-semitone pitch envelope, attack and decay in
  musical lengths, sixteen equal sample zones.
- Performance page (PErF): octave shifts, master gate, beat repeat, vinyl stop,
  backcue and scratch; hold MUTE to mute parts and MEMORY to choose a pattern
  or song without leaving the page.
- rb.ty: native reverbs, mono lo-fi delay and freeze with speed and direction.
- Audio pattern backup of the ten memories and the pattern in use, requested by
  VolcaStudio XL over MIDI.
- Startup text **dAtAbEAt OS** in the native seven-segment font.
- Firmware image SHA-256 `13c0652b2b2b25029652282cd24d8f5915866cbc770ac268e09e2e6e603ba918`;
  updater WAV SHA-256 `d5d51b357869c68c7dfd76116eb28f0ae19225ff97a9c3716b84777dabacba52`.
  See the [technical notes](docs/TECHNICAL.md).
