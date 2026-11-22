# Changelog

DataBeat OS is installed with
[VolcaStudio XL](https://micheledatabeat.github.io/volcastudio-xl-releases/),
which builds it from Korg's own volca sample System Updater 1.42.

## 1.1 — 22 November 2026

Installed with VolcaStudio XL 1.2. Compared with DataBeat OS 1.0:

**Added**

- LIVE has five pages: turn SAMPLE/SELECT for PErF, PErF., PEr3, PEr4 and PEr5.
  PErF. holds transpositions of a fourth and a fifth, vinyl stops and backcues
  that come back on the next bar, and scratches. PEr3 holds thirteen moving
  filters and three LoFi strengths. PEr4 and PEr5 hold thirty-two scratch
  gestures.
- Global mutes: hold MUTE on any LIVE page, or open GLob, and pads 1–10 switch
  the global mutes of parts 1–10. A global mute holds its part silent across
  memories, song positions, Stop and PLAY. WRITE does not save global mutes;
  they are all off at power-on.
- SonG builds a song on the Volca from up to sixteen memory positions.
  WRITE + pad 11–16 saves it in one of the six song slots.
- Echo with two spacings for each part, A on pads 1–8 and B on pads 9–16. With
  STEP on, each step chooses OFF, A, B or its own 1–4 echoes on B.
- Ratchet for each step: with STEP on, `r.01`–`r.04` give a step its own number
  of hits, `r.00` follows the part.
- AStP, a page for the active steps. From LIVE, REC opens it and REC goes back.
- The bar filter has sixteen bars for each part.

**Changed**

- Echo spacings: 1/32, 1/16 triplet, 1/16, 1/8 triplet, 1/8, dotted 1/8, 1/4
  and 1/2. The dotted 1/4 and one-bar spacings are gone.
- Inside LIVE, MUTE held sets the global mutes; outside LIVE, MUTE keeps
  controlling the pattern's part mutes.
- The active steps live on AStP: FUNC + PLAY stays PLAY.
- Patterns use the DataBeat OS 1.1 format. Patterns saved with DataBeat OS 1.0
  play after VolcaStudio XL 1.2 converts them; for a part on the dotted 1/4 or
  one-bar spacing you choose the new spacing.

**Removed**

- The factory patterns: loading one gives an empty memory. VolcaStudio XL 1.2
  rebuilds them from your Korg updater as a DataBeat OS 1.1 bank, set 1 or
  set 2.
- Step recording (FUNC + REC) and the step jump (FUNC + STEP).

**Fixed**

- Leaving a page: with STEP on, the pads stayed dark until you pressed STEP
  twice, though the STEP light was lit. While you played with STEP off, the
  part flashes came back only at the next step. Now the selected part's notes
  and the part flashes come back as soon as you leave the page.
- LOOP, REVERSE and the effect send of a part: a note moved by Time, a note
  with Echo or Ratchet, an early note and the note that ends a backcue played
  with these switches as the last WRITE had saved them. These notes now follow
  the panel at once, saved or not. A switch pressed in the last 15/32 of a step
  before a note that Time moves earlier reaches the next note instead.
- Freeze: a note moved by Time or with Echo or Ratchet entered a freeze capture
  at the REVERB MIX level, and hardly at all with MIX low. Such notes now enter
  at full send, like the other notes.
- Long vinyl stops and backcues with the Volca on its own clock: when a brake
  overloaded a busy pattern, the sequencer fell behind. After the brake it ran
  through the steps it had missed and played them in a rush, and MIDI clock and
  SYNC OUT rushed with it. Now the Volca catches up at once. MIDI clock and SYNC
  OUT stay on time, the steps that fall inside the catch-up stay silent, and
  after the brake the pattern is back on its original bar, with no rushed or
  added notes.
- Long vinyl stops with the Volca following SYNC IN: on a busy pattern, every
  other step during the stop played late, by up to about 0.1 s. Those steps are
  now at most 4 ms late. Both figures were measured in emulation.
- MIDI: as in Korg's firmware, data bytes received after power-on and before
  any status byte could run the MIDI parser past its buffer and overwrite
  memory the panel uses. The fault was measured in emulation and never seen on
  the Volca. Such bytes are now ignored, as MIDI 1.0 asks.

Firmware image SHA-256 `5d2dd053563bc76b2106f87393984039c44b7d1876dc1846b837a89c1ebc4ef1`;
updater WAV SHA-256 `b0fa3052173bd9ff192f8f4bc2c3843c6dd407ef7bf991203f92acd75336bf8c`.
See the [technical notes](docs/TECHNICAL.md).

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
