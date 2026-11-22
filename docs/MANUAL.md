# DataBeat OS 1.1 — manual

For the first-generation Korg Volca Sample. At startup the display scrolls
**dAtAbEAt OS**.

A [DataBeat](https://micheledatabeat.github.io/) project, not affiliated with
Korg. VolcaStudio XL installs DataBeat OS 1.1: see the
[installation guide](INSTALL.md). To go back to the Korg firmware, power on with
**MEMORY + PLAY** and send the original Korg updater from Studio: see
[Return to Korg firmware](RETURN-TO-KORG.md).

## What DataBeat OS changes

**Added to the Korg firmware:**

- five pages of LIVE effects, held on the pads: octaves, beat repeat, vinyl
  stops, backcues and scratches on PErF and PErF.; moving filters and LoFi on
  PEr3; thirty-two scratch gestures on PEr4 and PEr5;
- global mutes, which hold a part silent across memories and songs;
- [Predictability](#predictability-choose-which-bars-play-a-step), with 24
  choices over eight bars for each step, and a
  [bar filter](#bar-filter-leave-a-whole-part-out-of-a-bar) of sixteen bars for
  each part;
- [Time](#time-move-a-step-earlier-or-later), to move each step earlier or later;
- [Echo](#echo-add-quieter-hits-after-each-note) with two spacings and
  [Ratchet](#ratchet-divide-each-note-into-repeated-hits), for each part and for
  each step;
- the [intra-bar loop](#intra-bar-loop-repeat-part-of-the-pattern);
- [scales, musical envelope lengths and sample zones](#scales-pitch-envelope-and-sample-zones);
- [delay and freeze](#rbty-reverb-delay-and-freeze) next to the reverbs;
- [songs](#song-play-memories-in-a-chain) built on the Volca, from up to sixteen
  memory positions.

**Moved or working differently:**

- FUNC stays on after one press, and the extension pages open from it. LIVE is
  the first page.
- The active steps (FUNC + PLAY on the Korg firmware) have their own page,
  [AStP](#active-steps-shorten-the-cycle). From LIVE, REC opens it.
- Inside LIVE, MUTE held sets the global mutes, MEMORY held chooses a pattern
  and STEP sets the loop.
- Patterns are stored in the LMX6 format. Patterns from DataBeat OS 1.0
  need converting first: see [patterns and Studio](#patterns-and-studio).

**Not available:**

- the factory patterns: loading one gives you an empty memory (VolcaStudio XL
  rebuilds them as a bank: see [patterns and Studio](#patterns-and-studio));
- step recording with FUNC + REC;
- the step jump with FUNC + STEP.

## Editing and saving

**Your edits change the pattern currently in use.** You can keep playing,
leave an extension page and return without pressing WRITE. Changes follow the
timing of the notes and effects they control. Notes already prepared for
playback may keep their previous settings; loop changes follow the boundary
rules described below.

**LOOP, REVERSE and the effect send of a part act at once, saved or not.**
Turn one of them on or off and the part's next note follows it, including a
note that Time moves and a note with Echo or Ratchet. Echoes and ratchet hits
keep the switches of their own note. A note that Time moves
earlier is prepared 15/32 of a step before its step, so a switch pressed in
that last stretch (about 80 ms at 88 BPM) reaches the following note. When
another memory loads, an early note of its first step already plays with the
switches saved in the memory that arrives.

**WRITE saves the whole pattern to a memory, as on the standard Volca Sample.**
Use it when you want to recall that version of the pattern later. The extra
functions apply as you set them, without WRITE. Because FUNC stays on after one
press, the save completes even if FUNC is still on or you enter an extension
page while it runs.

For example, give a kick step P.03, leave PrEd and play: that choice is already
part of the current pattern. Save the pattern with WRITE when you want to
recall that version from a memory.

Here, a **part** is one of the ten sound parts; a **step** is one of the sixteen
sequencer positions. The pages control different things:

| Setting | Applies to |
| --- | --- |
| Predictability, Time | Each step of each part |
| Echo state and Ratchet hits for a step (STEP on) | Each step of each part |
| Bar filter, Echo (number, spacings A and B), Ratchet, scale | The selected part |
| Intra-bar loop | The whole pattern |
| Active steps | The whole pattern |
| Pattern mutes (MUTE and a pad outside LIVE) | Each part; saved in the pattern |
| Global mutes (MUTE held in LIVE, or GLob) | Each part across memories; not saved in the pattern |
| LIVE gestures | The current performance; not stored in the pattern |
| rb.ty program, delay/freeze duration and playback controls | The current effect; not stored in the pattern |
| Captured freeze audio | A temporary recording; not stored in the pattern |

WRITE saves every setting from the top of the table down to the pattern mutes.
Loading the memory brings them back: a part muted when you save stays muted
when you load that memory again.

Global mutes are separate. WRITE does not store them, loading a memory does
not change them, and they are all off when the Volca is switched on.
Sample audio and global settings are separate from pattern memories.

## Opening and leaving a page

FUNC stays on after one press. Press it again to turn it off.

1. Select the part you want to edit.
2. Press FUNC to turn it on.
3. Turn SAMPLE/SELECT to choose an extension page.
4. **Press FUNC again to enter that page.**

Inside a page, **PART <** and **PART >** still change the part, and the page
follows it: the display stays on the page and shows the new part's values (the
bar filter shows its number), and LIVE beat repeat uses it from the next pad
press.

While you choose a page, the FUNC light stays on. Inside a page it blinks;
in LIVE the MUTE light blinks too.

LIVE is the first page in the menu. It opens on PErF. Turn SAMPLE/SELECT inside
LIVE to reach PErF. with a point, then **PEr3**, **PEr4** and **PEr5**.

If you start WRITE (FUNC + MEMORY) while choosing a page, entering the page
cancels it, as pressing FUNC does on the standard Volca Sample. Its lights stop
blinking and nothing is saved.

With FUNC on, STEP and PLAY do what they do without FUNC: STEP turns STEP
editing on and off, PLAY starts and stops. The step jump (FUNC + STEP) is not
available, and FUNC + PLAY stays PLAY: the active steps are on the
[AStP page](#active-steps-shorten-the-cycle). Active steps already saved in a
pattern play as saved, and AStP changes them again.

To leave a page, press FUNC. This returns to page selection with FUNC on.
Press FUNC once more to return to ordinary controls.

| Page | SAMPLE/SELECT | Pads |
| --- | --- | --- |
| LIVE | With STEP off: five pages, from PErF to PEr5; with STEP on: OFF or 1–16 loop passes | Hold an effect; hold MUTE for global mutes; hold MEMORY to choose a pattern; with STEP on, set the loop |
| PrEd | Change Predictability for the steps you hold | Hold one or more steps |
| Bar filter | — | Toggle bars 1–16 |
| rb.ty | Choose reverb 0–2, delay 3 or freeze 4 | Set duration and control freeze |
| tIME | Change microtiming for the steps you hold | Hold one or more steps |
| ECho | Choose 0–4 extra hits; with STEP on and steps held, their Echo: OFF, A.--, b.--, b.01–b.04 | Pads 1–8 choose spacing A, pads 9–16 spacing B; with STEP on, hold steps |
| rAtC | Choose 1–4 hits within a step; with STEP on and steps held, their own hits | Pads 1–4 choose the same hit count; with STEP on, hold steps |
| LooP | Set OFF or 1–16 total passes | Hold the first and last steps of the loop |
| SCAL | Choose scale 0–15 | Pads 1–16 choose the same scales |
| SonG | Choose memory 1–10 for the selected position; below 1 removes it | Pad 1 starts a song; select a position or add the next one |
| AStP | — | Switch steps 1–16 on and off for the whole pattern; the lit pads are the steps that play |
| GLob | — | Pads 1–10 switch the global mutes of parts 1–10 |

With STEP on, PrEd and Time show the selected part's programmed notes once
you have entered the page with the second FUNC press. The note map is hidden
while you are still choosing a page with FUNC on.

Inside PrEd and Time, pads select steps for that page's parameter. They do
not add or remove notes. The other parameter knobs are suspended until you
leave the page. A knob moved during this time can apply its current position
when ordinary control resumes. With STEP off, only the pads you hold are lit.

Outside extension pages, STEP editing keeps its ordinary role. With STEP and
FUNC both on, pads still edit notes while FUNC changes the knobs' functions.
You arrive here when you leave LIVE with STEP still on after setting the loop
there: turn STEP off before pressing FUNC if you only want to change page.

## Predictability: choose which bars play a step

Predictability repeats over eight bars. Each step of each part has its
own choice: ALL plus P.01–P.23, making 24 choices in total.

For example, put a kick on step 1 and give it P.03. It plays on bars 1 and 5.
Give another kick step ALL and it plays on every bar, subject to the part's
bar filter.

1. Open PrEd for the part you want to edit.
2. Hold one or more step pads.
3. Turn SAMPLE/SELECT to change the choice for those steps.

The display shows the choice of the lowest-numbered pad you hold. Turning
without holding a pad changes nothing. Setting a choice on an empty step does
not create a note. Initializing a pattern sets every choice to ALL.

Read left to right: each symbol is one bar, from 1 to 8. `X` allows the step
to play; `0` skips it. All parts share the same bar count.

| Setting | Bars 1–8 |
| --- | --- |
| ALL | `XXXXXXXX` |
| P.01 | `X0000000` |
| P.02 | `0000000X` |
| P.03 | `X000X000` |
| P.04 | `000X000X` |
| P.05 | `X0X0X000` |
| P.06 | `000X0X0X` |
| P.07 | `X0X000X0` |
| P.08 | `X00X00X0` |
| P.09 | `X000X0X0` |
| P.10 | `X0X0X0X0` |
| P.11 | `0XXXXXXX` |
| P.12 | `XXXXXXX0` |
| P.13 | `0XXX0XXX` |
| P.14 | `XXX0XXX0` |
| P.15 | `0X0X0XXX` |
| P.16 | `XXX0X0X0` |
| P.17 | `0X0XXX0X` |
| P.18 | `0XX0XX0X` |
| P.19 | `0XXX0X0X` |
| P.20 | `0X0X0X0X` |
| P.21 | `XXXX0000` |
| P.22 | `0000XXXX` |
| P.23 | `00X00X00` |

## Bar filter: leave a whole part out of a bar

The bar filter has sixteen independent choices for each part: pad 1 is
bar 1 and pad 16 is bar 16. Open its page and press a pad to allow or exclude
the part in that bar. Lit means allowed; unlit means excluded. After bar 16
the count starts again at bar 1.

Exclude bar 12 for the kick: the kick drops out once in a
sixteen-bar phrase, and bar 4 still plays it. Predictability counts eight bars,
so its sequences repeat twice in the sixteen bars of the filter.
Predictability and the bar filter both have to allow the original note.
If that note is skipped, its echoes and ratchets are skipped too. An excluded
open hi-hat does not suppress a closed hi-hat that is allowed to play.

Stop/Start restarts the bar count at bar 1. An intra-bar loop completes its
repeats before the count advances; each internal return stays in the same bar.
Manual triggers and LIVE beat repeat are independent of these two filters.

## Time: move a step earlier or later

Open tIME, hold the step pads you want to edit and turn SAMPLE/SELECT.
Negative values move hits earlier; positive values move them later. Zero keeps
their ordinary timing. The display shows the value of the lowest-numbered pad
you hold, even if an earlier step is lit in the note map.

Each step of each part has its own value, from −15 to +15. One unit is
1/32 of that step's duration. For example, +4 delays a hit by one eighth of
its step. Swing is included in that duration.

## Echo: add quieter hits after each note

Echo is set for each part, with two spacings, A and B. With STEP on,
each step chooses between them, switches its echoes off or gets its own
number of echoes. On ECho, turn SAMPLE/SELECT to choose 0–4 extra hits
(the display shows `E.04`). Zero adds none. Each echo is quieter than the
previous hit. Pads 1–8 choose spacing A, pads 9–16 spacing B, with the
same eight values; the two chosen pads are lit:

| Pad A | Pad B | Note value without swing | Spacing in steps |
| --- | --- | --- | --- |
| 1 | 9 | 1/32 | 1/2 |
| 2 | 10 | 1/16 triplet | 2/3 |
| 3 | 11 | 1/16 | 1 |
| 4 | 12 | 1/8 triplet | 4/3 |
| 5 | 13 | 1/8 | 2 |
| 6 | 14 | Dotted 1/8 | 3 |
| 7 | 15 | 1/4 | 4 |
| 8 | 16 | 1/2 | 8 |

For example, choose 2 and pad 5: each original note of this part is followed
by two quieter hits, spaced two steps apart. The spacing follows the original
note's step duration, including swing. Echoes use that note's sound settings.
The triplets are rounded to the nearest tick of the internal clock (half a
millisecond): the fourth echo is at most about 0.7 ms early or late.

### Echo step by step: press STEP

Inside ECho, press **STEP**. The pads now show the notes of the selected
part, as in PrEd and Time; they never show the Echo values, and changing a
value changes no light. Pressing a pad only selects its step, also a step
without a note, which lights only while you hold it. Hold one or more steps and
turn SAMPLE/SELECT: each held step moves from its own value, in this order,
and stops at both ends:

`OFF` ← `A.--` → `b.--` → `b.01` → `b.02` → `b.03` → `b.04`

| Display | The step's notes |
| --- | --- |
| `A.--` | the part's number of echoes on spacing A (the default) |
| `OFF` | no echo |
| `b.--` | the part's number of echoes on spacing B |
| `b.01`–`b.04` | 1–4 echoes on spacing B, whatever the part's number, also 0 |

While you hold steps the display shows the lowest step you hold; with no step
held it shows `E.0n` and SAMPLE/SELECT changes the part's number of echoes, as
with STEP off. Press STEP again to go back to the spacing pads.

For example, notes on steps 1, 5, 9 and 13 of a part, 4 echoes, pad 3 (A,
1/16) and pad 13 (B, 1/8). Press STEP, hold step 1 and turn two clicks right:
`b.--`, then `b.01`; one more click: `b.02`. Hold step 5 and turn one click
left: `OFF`. Hold step 9 and turn one click right: `b.--`. Step 13 stays on
`A.--`. You hear step 1 with 2 echoes an eighth apart, step 5 dry, step 9 with
4 echoes an eighth apart and step 13 with 4 echoes a sixteenth apart. With the
part at 0 echoes, steps on `A.--` and `b.--` are dry, and a step on `b.02`
still gets its 2 echoes. That way a single hit can have an echo while the rest
of the part stays dry.

A new pattern has every step on `A.--`, the part at 0 echoes and both
spacings at 1/32, so it plays dry. 0 echoes and `OFF` sound the same.
WRITE saves the steps' Echo and both spacings with the pattern.

Leaving the page with FUNC keeps STEP on, as in Time; turn STEP off before
editing notes again if you do not want to write steps.

## Ratchet: divide each note into repeated hits

Ratchet is set for each part, and with STEP on each step can have its
own number of hits. On rAtC, press pad 1, 2, 3 or 4, or turn SAMPLE/SELECT,
to choose one, two, three or four hits within a step. The number includes
the original hit: 1 is ordinary playback, with no repeats.

Choose 3 for the snare part. Each programmed snare note that is
allowed to play becomes three evenly spaced hits within its step. Other parts
keep their own ratchet settings.

### Ratchet step by step: press STEP

Inside rAtC, press **STEP**. The pads now show the steps that have their own
number of hits. Hold one or more steps and turn SAMPLE/SELECT: each held step
moves from its own value, from `r.00` to `r.04`. `r.00` means **as the part**:
the step follows the part's setting; `r.01` to `r.04` give that step one to
four hits, whatever the part says. While you hold steps the display shows the
lowest step you hold; with no step held it shows the part's own value, and
SAMPLE/SELECT changes the part as outside STEP. Pressing pads without turning
only selects them. Press STEP again to go back.

With a snare at one hit, press STEP, hold step 15 and turn to
`r.04`. The snare plays single hits all bar long and a four-hit roll on step 15
into the next bar.

### Timing limits

Echoes and ratchets follow the original sequenced note: if that note is
filtered out, its repetitions do not play. A muted part stays muted.

A very short preceding step can limit how far a hit can be moved early.
Extreme swing, clock changes and dense combinations can affect timing.
The number of scheduled hits and sounding voices is finite: some echoes can
be dropped, and a new voice can replace an older one.

## Active steps: shorten the cycle

Open **AStP**, after SonG in the menu. The lit pads are the steps that play.
Press a pad to switch its step off or on again; press several pads together to
switch them all. The change is heard at once, also while the pattern plays.
The last step left on does not go off, as on the standard Volca Sample.
SAMPLE/SELECT does nothing here, and PART < and PART > change nothing on the
page: the active steps belong to the whole pattern, all ten parts together.

A step that is off is skipped: switch off step 5 and step 6 comes right after
step 4, so the cycle gets shorter. With three steps off the cycle lasts 13
steps. The notes of a step that is off stay in the pattern: switch the step on
again and they come back.

Echo and Ratchet follow time, not steps: an echo one step after step 4 sounds
together with step 6 when step 5 is off, and a ratchet still divides its own
step. The intra-bar loop ends on the last active step inside it: LooP 1–8 with
step 8 off repeats a cycle of 7 steps. For example, set LooP 1–8 with three
passes, then switch off step 8 in AStP: the pattern plays 1–7 three times,
then 9–16, an odd phrase of 29 steps.

WRITE saves the active steps in the pattern. In a song each memory brings its
own active steps, as its mutes and loop do: changes made without WRITE are lost
when another memory loads.

From LIVE, **REC** opens AStP and REC in AStP goes back to LIVE: see
[REC: jump to the active steps](#rec-jump-to-the-active-steps).

## Intra-bar loop: repeat part of the pattern

Open LooP, then hold the first and last steps you want to repeat. If you hold
more than two pads, the outermost ones set the interval; one pad selects a
single-step loop. Turn SAMPLE/SELECT for 1–16 total passes, or below 1
for OFF. Inside LIVE, STEP on gives you the same controls without leaving the
page; see [setting the loop from LIVE](#setting-the-loop-from-live).

Steps 1–8 with three passes play:
`1…8, 1…8, 1…8, 9…16`. One pass adds no repeat. OFF keeps the interval visible
without repeating it. New patterns start with steps 1–8, a pass count of three
and the loop OFF. Interval, count and ON/OFF choice belong to the current pattern.

Loop edits take effect after the next boundary the sequencer has already
selected. Notes moved early can finish a return that was already prepared.
An interval with no enabled steps is bypassed. A pending pattern or song
change takes priority. Stop/Start and pattern load rearm the loop from the
current pattern's settings. In a song, the next position starts after the
complete expanded phrase; a position with the same memory keeps the loop
running, another memory rearms it from that memory's settings.

Saving with WRITE and taking an audio backup briefly suspend the loop, then
rearm it, unless an explicit cancellation has disabled that return.
Saving does not cancel a LIVE effect you are holding. LIVE presses, replacements
and releases keep the loop interval and remaining passes. Enabling a loop or
changing an enabled loop cancels LIVE.

## Scales, pitch envelope and sample zones

SCAL chooses a scale for the selected part. Use SAMPLE/SELECT for 0–15
or pads 1–16 for the same choices: pad 1 selects scale 0, pad 16 selects
scale 15. The scale maps semitone-mode SPEED relative to the sample's original
pitch; it does not detect or tune its root note. FUNC+SPEED remains continuous.

| Number | Scale |
| --- | --- |
| 0 | Chromatic |
| 1 | Major / Ionian |
| 2 | Natural minor / Aeolian |
| 3 | Dorian |
| 4 | Phrygian |
| 5 | Lydian |
| 6 | Mixolydian |
| 7 | Locrian |
| 8 | Harmonic minor |
| 9 | Melodic minor, ascending |
| 10 | Major pentatonic |
| 11 | Minor pentatonic |
| 12 | Minor blues |
| 13 | Whole tone |
| 14 | Diminished, whole–half |
| 15 | Diminished, half–whole |

PITCH EG INT sets an envelope depth of about −24…+24 semitones, with zero
at the centre. ATTACK and DECAY choose musical lengths in these knob regions:

| Display code | Duration |
| --- | --- |
| 0 | Instant |
| 1 | 1/16 |
| 2 | 1/8 |
| 3 | Dotted 1/8 |
| 4 | 1/4 |
| 5 | Dotted 1/4 |
| 6 | 1/2 |
| 7 | One bar |

These lengths follow the straight clock before swing. With FUNC, ATTACK and
DECAY keep free timing. Free envelope values saved in a pattern stay free until
you edit them; motion and held-step editing keep the chosen musical or free
mode. The pitch envelope moves continuously between its endpoints,
independently of the scale.

FUNC+START and FUNC+LENGTH choose the start and end from sixteen equal zones
of the sample. The end cannot come before the start. The ordinary knobs keep
their continuous sample controls. Zone choices also work with motion.

## LIVE: temporary performance effects

Select a part, open LIVE and hold a pad. Pads 4–7 affect only the selected
part. The others affect all parts or the stereo master, as listed.
LIVE gestures are not stored in the pattern.

| Pad | Effect |
| --- | --- |
| 1 | All sounding voices one octave down, at half playback speed |
| 2 | All sounding voices one octave up, at double playback speed |
| 3 | Master gate: silence the stereo output in the second half of each swung step |
| 4–7 | Selected-part beat repeat at 1/8, 1/16, 1/32 or 1/64 |
| 8 | Vinyl stop, 1/2 note; return at the next qualifying sequenced note |
| 9 | Vinyl stop, 1/4 note; return at the next qualifying sequenced note |
| 10 | Vinyl stop, 1/8 note; return at the next qualifying sequenced note |
| 11 | Vinyl stop, 1/16 note; return at the next qualifying sequenced note |
| 12 | Backcue, 1/2 note; return at the next qualifying sequenced note |
| 13 | Backcue, 1/4 note; return at the next qualifying sequenced note |
| 14 | Backcue, 1/8 note; return at the next qualifying sequenced note |
| 15 | Backcue, 1/16 note; return at the next qualifying sequenced note |
| 16 | Scratch: repeated 1/16 braking with decreasing volume |

Only one LIVE effect runs at a time. Pressing a new pad replaces the current
effect. Releasing that pad does not bring back an older one you are still
holding. If several new pads arrive together, the lowest-numbered one wins.

### Turning the LIVE pages

In LIVE with STEP off, turn SAMPLE/SELECT clockwise to move through:

**PErF → PErF. → PEr3 → PEr4 → PEr5**

Turn counterclockwise to go back. Each click moves one page. More clicks past
PErF or PEr5 do nothing. With STEP on, SAMPLE/SELECT keeps setting the loop
passes. With MUTE or MEMORY held, it does not change the page.

Changing page ends the effect you are holding. A pad still down does not
start the new page's effect: release it and press again. LIVE always opens
on PErF. FUNC leaves every page in the same way.

MUTE, MEMORY and STEP return you to the LIVE page you were on. REC opens AStP;
REC there returns to that same LIVE page. PART < and PART > still choose the
part, without selecting a different LIVE page. The FUNC light blinks and the
pad of the running effect is lit on every LIVE page.

### PErF.: the second page of effects

PErF. is the second page of LIVE effects, with the point on the F. From PErF,
one SAMPLE/SELECT click clockwise opens it. One click counterclockwise goes
back. Another clockwise click opens **PEr3**. The controls follow
[the five-page order](#turning-the-live-pages).

The pads follow the first page's order: down before up, as octave − and + on
pads 1–2, vinyl stop before backcue, and the longest length first, as on pads
8–11 and 12–15.

| Pad | Effect |
| --- | --- |
| 1 | All sounding voices 7 semitones down while you hold |
| 2 | 5 semitones down |
| 3 | 5 semitones up |
| 4 | 7 semitones up |
| 5 | Vinyl stop of one bar; return on the bar |
| 6 | Vinyl stop, 1/2 note; return on the bar |
| 7 | Vinyl stop, 1/4 note; return on the bar |
| 8 | Vinyl stop, 1/8 note; return on the bar |
| 9 | Backcue of one bar; return on the bar |
| 10 | Backcue, 1/2 note; return on the bar |
| 11 | Backcue, 1/4 note; return on the bar |
| 12 | Backcue, 1/8 note; return on the bar |
| 13 | Scratch, a braking ramp every 1/8 |
| 14 | Scratch, a braking ramp every 1/16 triplet |
| 15 | Baby scratch: back and forth, a ramp every 1/8 |
| 16 | Baby scratch: back and forth, a ramp every 1/16 |

**Transpositions, pads 1–4.** Every sounding voice plays at a fixed ratio
while you hold the pad: −7 semitones is a fifth down, +7 a fifth up, −5 and +5
a fourth. They work like the octaves of pads 1–2 of the first page: notes keep
their pitch envelope and SPEED, fading tails move too, release to go back to
ordinary speed, and samples continue from where they are. Going up, a sample
reaches its end sooner: a short one-shot at +7 stops about a third earlier.
Reverb, delay and freeze audio already captured keeps its own rate.

**Return on the bar, pads 5–12.** These brake like pads 8–15 of the first
page, then the music comes back on the 1 of the next bar:

- if the brake ends before the bar, the output stays silent until the 1;
- if the brake is still running when the 1 arrives, it is cut there;
- from the 1, the first qualifying original note returns, with the same
  conditions as on the first page (Predictability, bar filter, enabled and
  unmuted part, sample and volume, exclusive hi-hats).

For example, with the kick on every beat: press the 1/4 vinyl stop (pad 7) on
the fourth beat. You hear a quarter note of brake, and the kick starts again
on the 1. Pressed on the second beat, the brake ends on the third: the kicks
of the third and fourth beats stay silent and the music returns on the 1. A
one-bar vinyl stop (pad 5) pressed just after the 1 brakes the whole bar and
the music is back on the next 1. Release the pad before the brake ends to
restore ordinary playback at once; after it, the music waits for the 1.

**The bar** is the real turn of the pattern: with 16 steps the 4/4 bar, with
steps switched off in AStP the shorter cycle (12 steps, for example). The
returns of the intra-bar loop are not bars: with the loop on steps 1–8 for
three passes the cycle is 32 steps (1–8 three times, then 9–16), and the
music comes back on the 1 after the whole cycle. Stopping the sequencer, a
pattern load or a song position with another memory ends the effect, as on
the first page.

**Scratch, pads 13–16.** Like pad 16 of the first page, with the volume falling
over eight ramps. Pad 13 restarts the ramp every 1/8, pad 14 every 1/16
triplet (three in the time of two sixteenths). The baby scratches play every
second ramp forward: back, forward, back, forward, every 1/8 on pad 15 and
every 1/16 on pad 16. Release to wait for the next qualifying note, as on the
first page.

Lengths are measured from the clock when you press the pad, before swing. With
a very slow external clock, below about 7.3 BPM, a one-bar brake would last
longer than the Volca can count and the press is ignored; the shorter ones
still work.

### PEr3: moving filters and LoFi

Open **PEr3**, after PErF. Hold a pad for a moving filter or for LoFi; release
it to go back to the dry sound. A new pad replaces the one that is running.

Filters and LoFi act on the mixed stereo output, left and right separately.
Each filter moves its cutoff in time with the tempo. A low-pass filter removes
the high end as it closes, a high-pass removes the low end as it rises, and a
band-pass keeps only a band of frequencies, which it moves up and down.

The movement starts from the bottom of its range when you press the pad.
Changing tempo changes the speed of the sweep without restarting it. Here a
bar is four quarter notes.

| Pad | Filter | Range | Full cycle of the movement |
| --- | --- | --- | --- |
| 1 | High-pass, slow rise | 60–5000 Hz | Rises and falls back over two bars |
| 2 | Band-pass wah | 400–2500 Hz | Opens and closes every quarter note |
| 3 | Band-pass wah | 400–2500 Hz | Opens and closes every half note |
| 4 | Band-pass radio, narrow | 900–1600 Hz | Moves slightly up and down over two bars |
| 5 | Low-pass dub sweep | 150–4000 Hz | Opens and closes over two bars |
| 6 | Low-pass dub sweep | 150–4000 Hz | Opens and closes over one bar |
| 7 | Low-pass | | Smoothly opens and closes over one bar |
| 8 | Low-pass | | Smoothly opens and closes every quarter note |
| 9 | Low-pass | | Rises and falls evenly over half a bar |
| 10 | Low-pass | | Closes over a quarter note, then jumps open again |
| 11 | Low-pass, breathing sweep | | Closes with a curved fall over one bar, then opens again |
| 12 | High-pass | | Smoothly rises and falls over one bar |
| 13 | Band-pass | | Smoothly rises and falls over two bars |

No filter on this page goes over 0 dBFS, whatever comes in. Each filter
lowers its input by just enough. The low-pass pads (5–11) sound about 3 dB
below the dry signal, the high-pass pads (1 and 12) about 8 dB below, and the
band-pass pads (2–4 and 13) about 3 dB below at the centre of their band and
quieter away from it, because they keep only part of the sound.

Pads 14–16 are the LoFi. They make the sound coarser, with fewer level steps,
and hold each sample for more than one sample period:

| Pad | Effect while held |
| --- | --- |
| 14 | Light LoFi: 12-bit steps, each sample held twice |
| 15 | Medium LoFi: 8-bit steps, each sample held 4 times |
| 16 | Strong LoFi: 5-bit steps, each sample held 4 times |

Before the hold, pads 15 and 16 pass the sound through a low-pass at 2.7 kHz,
so hi-hats do not turn into clicks. They sound slightly darker and about
1.3 dB lower than the dry signal.

A filter starts from the sound already playing and comes in over about 15 ms.
The LoFi comes in over about half a millisecond, and every effect goes out
in about half a millisecond. Moving between two low-pass pads, or between the
two high-pass pads, the filter carries on with the new movement; moving
between LoFi pads, the new setting starts at once. Any other change, between
two band-pass pads, between filter types or between a filter and the LoFi,
passes through the dry signal.

**Voices on PEr3.** While a PEr3 effect is active, playback uses up to seven
voices. If eight voices are sounding when you engage it, the oldest voice is
stopped. Once the effect has ended, eight voices are available again, and a new
note can take the freed slot. PErF, PErF., PEr4 and PEr5 keep all eight voices.

### PEr4 and PEr5: scratch gestures

Open **PEr4** or **PEr5**. These gestures move all sounding voices together,
like the scratches of PErF. Hold a pad to play; release to leave the gesture.
They never latch.

A gesture starts with the press. Its duration comes from the clock at that
moment, before swing, except scribble (PEr4, pad 16), which has a fixed speed.
It repeats while you hold, except tape start: that accelerates once and then
keeps normal playback speed. The open sound stays at its level while you hold;
it does not fade through eight cycles like the scratches on PErF and PErF.

On both pages, pads 1–15 come in groups of three neighbouring pads: the same
technique with a calm, medium or strong hand. They change the push, not the
musical duration. Pad 16 has one technique on each page. The return is faster
than the forward stroke and covers the same stretch in less time. The time
left over becomes a pause within the cycle.

| Intensity | Most techniques: forward / back | Drags and transformer: forward / back |
| --- | --- | --- |
| Calm | 1.5× / 2× | 0.45× / 0.6× |
| Medium | 2.5× / 3× | 0.6× / 0.8× |
| Strong | 3× / 4× | 0.75× / 1× |

**PEr4.**

| Pad | Gesture | Full cycle |
| --- | --- | --- |
| 1 | Baby, calm | 1/8 |
| 2 | Baby, medium | 1/8 |
| 3 | Baby, strong | 1/8 |
| 4 | Tear, calm | 1/8 |
| 5 | Tear, medium | 1/8 |
| 6 | Tear, strong | 1/8 |
| 7 | Drag, calm | 1/2 bar: forward for one quarter-note, back in the next |
| 8 | Drag, medium | 1/2 bar: forward for one quarter-note, back in the next |
| 9 | Drag, strong | 1/2 bar: forward for one quarter-note, back in the next |
| 10 | Stab, calm | 1/8 |
| 11 | Stab, medium | 1/8 |
| 12 | Stab, strong | 1/8 |
| 13 | Transformer, calm | Half a bar |
| 14 | Transformer, medium | Half a bar |
| 15 | Transformer, strong | Half a bar |
| 16 | Scribble | About 45 ms, at any tempo |

**Baby** moves forward over a sixteenth and returns within the next
sixteenth: the complete cycle is an eighth. **Tear** breaks the return into
three pieces. **Drag** uses a slow hand. **Stab** opens the forward stroke and
closes the return. **Transformer** cuts a slow movement into short openings.
**Scribble** makes fast, small forward and backward movements over a slow
forward drift.

**PEr5.**

| Pad | Gesture | Full cycle |
| --- | --- | --- |
| 1 | Chirp, calm | 1/16 |
| 2 | Chirp, medium | 1/16 |
| 3 | Chirp, strong | 1/16 |
| 4 | One-click flare, calm | 1/8 |
| 5 | One-click flare, medium | 1/8 |
| 6 | One-click flare, strong | 1/8 |
| 7 | Two-click flare, calm | 1/8 |
| 8 | Two-click flare, medium | 1/8 |
| 9 | Two-click flare, strong | 1/8 |
| 10 | Triplet flare, calm | One third of a bar |
| 11 | Triplet flare, medium | One third of a bar |
| 12 | Triplet flare, strong | One third of a bar |
| 13 | Crab, calm | 1/4 |
| 14 | Crab, medium | 1/4 |
| 15 | Crab, strong | 1/4 |
| 16 | Tape start | Accelerates over 1/8, then continues at normal speed |

**Chirp** cuts a short forward stroke. **One-click flare** closes and opens
the sound once in each stroke; **two-click flare** does it twice. **Triplet
flare** puts the clicks in a three-against-four cycle. **Crab** makes four
fast clicks in the forward stroke. **Tape start** begins from standstill;
a new press starts the acceleration again.

The two-click flare (pads 7–9) keeps every click separate up to 300 BPM. The
one-click flare (pads 4–6) and the triplet flare (pads 10–12) have not been
checked at that tempo.

Release a gesture to wait for the next qualifying original sequenced note,
as on PErF. Until then, the output stays silent. Notes that start during a
gesture follow its movement. A voice that reaches its endpoint ends normally;
returning from the gesture does not restart it.

The sequencer must be running. Stop, a pattern load, leaving LIVE, changing
page, STEP and REC end the gesture. The usual LIVE rules still apply to MUTE,
MEMORY and the loop.

### Muting parts without leaving LIVE: global mutes

On any LIVE page, hold **MUTE** and press pads **1–10** to switch the global
mutes of parts 1–10. Release MUTE to return to the page you were on.

A part is silent if it is muted in the pattern or muted globally. Removing a
global mute does not remove a mute saved in the pattern. Changing a pattern
mute does not change its global mute.

While MUTE is held, the pads show both kinds:

| Pattern mute | Global mute | Pad light |
| --- | --- | --- |
| Off | Off | Dark |
| Off | On | Steadily lit |
| On | Off | Blinking |
| On | On | Blinking in the opposite phase: lit while the pattern-only blinking pads are dark |

Muting a part cuts it as the ordinary mute does. Turning LEVEL does not make
a globally muted part audible. Removing the global mute does not restart a
note already cut: the next note can play if the pattern also allows it.

Global mutes stay through memory changes, song positions, Stop and PLAY.
WRITE does not save them. At power-on they are all off.

Hold MUTE in LIVE and press the kick's pad. The kick stays muted
as the song moves through its memories. Press that pad again with MUTE held
to remove the global mute. If the current memory has its own kick mute, the
kick still stays silent.

An effect already held when you press MUTE keeps running under its usual
rules. Release its pad to release the effect, even while MUTE is held. That
already-held pad does not also switch a mute. A pad still down when you
release MUTE does not start an effect: release it and press again.

Outside LIVE, MUTE keeps controlling the pattern's ordinary part mutes.

### GLob: the global-mute page

Open **GLob**, after AStP in the extension menu. Pads 1–10 switch the same
global mutes, with the same lights as MUTE held in LIVE. Press FUNC to leave.
The global mutes stay as you set them.

### Choosing a pattern without leaving LIVE

Hold **MEMORY** and press a pad to choose a pattern, as outside LIVE. LIVE
stays open. When stopped, the pattern loads at once. While playing, it takes
over at the next step, or at the end of the bar during a song, which ends the
song. Pads 11–16 choose song 1–6 as outside LIVE; a song starts when the
current pattern ends.

Loading the pattern ends the running effect, and its pad light goes out.
A song that moves to a position with another memory loads it in the same way.
A position with the same memory keeps the effect running.
A pad that is still down when you release MEMORY does not start an effect:
release and press it again for a new LIVE gesture.

While MEMORY is held, every pad you hold counts, including the pad of a
running effect. The highest pad 1–10 chooses the pattern. If you hold only
pads 11–16, the highest chooses the song. Each press or release while
MEMORY is down chooses again. Releasing MEMORY confirms the choice. Release
the effect's pad first when you want a lower pattern.

### Setting the loop from LIVE

Press **STEP** inside LIVE to use the pads and SAMPLE/SELECT as on the LooP
page: hold the first and last steps of the interval, and turn SAMPLE/SELECT
for 1–16 passes, or below 1 for OFF. The display and pad lights are LooP's,
and the STEP light stays on. Turning STEP on ends the effect you are holding,
or one still waiting to return, as leaving LIVE does.

Press STEP again to return to the effects. The loop keeps running with its
interval and remaining passes, and the effects play over it. A pad still down
when you turn STEP off does not start an effect: release it and press it
again.

This is the pattern's own loop setting, the one LooP edits: WRITE saves it,
and it stays when you leave LIVE. Edits that LooP would refuse, for example
while WRITE is saving, are ignored here too.

MUTE and MEMORY work as described above while STEP is on; release them to
return to the loop controls. A pattern you load keeps STEP on and shows its
own loop. Choosing a song with pads 11–16 also keeps STEP on, and during a
song STEP works as with a pattern.

As in ordinary STEP editing, turning a knob while you hold pads stores its
value in those steps of the selected part as step motion. Set the interval
first and release the pads before you use the knobs. With no pad held, a knob
changes the part as usual.

If you leave LIVE with STEP on, PrEd and Time show the notes as usual, and
LIVE opens again with the loop controls.

### REC: jump to the active steps

On any LIVE page, press **REC**: the
[AStP page](#active-steps-shorten-the-cycle) opens at once, without the menu,
and REC stays off. Switch steps there, then press REC again to return to the
LIVE page you came from.

Opening AStP ends the effect you are holding, or one still waiting to return,
as leaving LIVE does. For example, with the kick on every beat and the hi-hat
on sixteenths: hold a beat repeat, let it go, press REC, switch off steps 13–16
(the cycle becomes 12 steps), press REC and you are back on the effects.

If REC was already on when you entered LIVE, the first REC switches it off as
usual and you stay in LIVE; the next one opens AStP. With MUTE or MEMORY held,
and outside LIVE and AStP, REC works as on the standard Volca Sample, apart
from step recording.

**Step recording is not available.** REC with FUNC on does nothing, so a FUNC
left on cannot turn a stopped Volca into step recording and rewrite a memory.
Recording while playing works as on the standard Volca Sample: turn REC on,
play, and the pads and knobs you play are recorded; REC armed while stopped
starts the sequencer from the first pad.

### Octaves and beat repeat

Pads 1–2 change sounding voices immediately, including fading tails. They
keep each note's pitch envelope and SPEED settings. Release to restore ordinary
speed; samples continue from their current positions rather than restarting.
Reverb, delay and freeze audio already captured keeps its own rate.
Samples still stop at their endpoints.

Beat repeat starts at the next step boundary and follows swing. While held,
it replaces the selected part's sequenced hits, echoes and ratchets, using
that part's current sound settings. Other parts keep playing. Mute, voice
limits and hi-hat exclusion still apply. Missed subdivisions are skipped.

### Vinyl stop and backcue

**Vinyl stop, pads 8–11**, slows each voice to zero in its current direction.
A forward-playing sample keeps moving forward; a sample already in reverse
keeps moving backward. **Backcue, pads 12–15**, reverses each voice's direction
while slowing it to zero. Both use the same four braking lengths:

| Note length | At 120 BPM |
| --- | --- |
| 1/2 | 1000 ms |
| 1/4 | 500 ms |
| 1/8 | 250 ms |
| 1/16 | 125 ms |

The length uses the clock at the moment you press the pad, before swing.
The sequencer must be running and a usable clock must be available.

Release before braking finishes to restore ordinary playback immediately.
After a complete brake, the output waits for the next qualifying original
sequenced note. That note must:

- pass Predictability and the part's bar filter;
- belong to an enabled, unmuted part;
- have an available sample and nonzero volume;
- survive the exclusive hi-hat rule.

The return happens at that note's scheduled time, including its Time offset.
Echoes, ratchets, manual triggers and beat repeat do not trigger this return.
The automatic return can happen while you still hold the pad. Release it and
press again to start another brake.

When this Volca runs on its own clock, a long brake on a busy pattern can
overload it. The Volca then catches up at once: MIDI clock and **SYNC OUT**
stay on time, the steps that fall inside the catch-up stay silent, and after
the brake the pattern is back on its original bar.

### Scratch

Pad 16 restarts a braking ramp every straight 1/16 while you hold it. The
master volume falls through 100%, 87.5%, 75%, 62.5%, 50%, 37.5%, 25% and 12.5%
over the first eight cycles, then reaches zero. The effect stays active and
silent while held.

Release to wait for the next qualifying original sequenced note, using the
same conditions above. Even a short scratch press waits for that note after
release. It then restores ordinary direction, speed and volume. Scratch acts
on the voices currently playing: it does not record a loop, reset sample
positions or restart voices that have ended.

### Endpoints, loops and leaving LIVE

A voice that reaches its sample endpoint ends normally; returning from a
LIVE effect does not restart it. Backcue can move a non-looped slice before
its selected start, within the original sample. Looped slices keep their bounds.
Scratch's volume change affects the stereo master, including effect tails.

Leaving LIVE, changing page in LIVE, turning STEP on, pressing Stop, loading
a pattern, initializing or starting an audio backup cancels LIVE and restores
ordinary playback without waiting for a musical boundary. In a song, a
position with another memory is a pattern load; a position with the same
memory is not. LIVE effects do not change the saved notes or motion. They
keep the intra-bar loop and its remaining passes as described in the loop
section. Global mutes remain separate from the effect you are holding.

## rb.ty: reverb, delay and freeze

Open rb.ty and turn SAMPLE/SELECT:

| Program | Effect |
| --- | --- |
| 0–2 | Native reverbs |
| 3 | Mono lo-fi delay |
| 4 | Freeze |

Only one of these programs runs at a time. LIVE can run alongside it.
Delay and freeze receive the mono effect send, not the whole stereo mix.
A part whose send is off remains audible directly but does not feed them.

The program, delay/freeze duration, speed, direction and stop state are live
effect controls, separate from pattern storage. WRITE does not store them or
the captured audio. Opening rb.ty again keeps the current effect; changing
to another program clears its audio history. Changing to delay starts with
two steps; changing to freeze starts with one step, normal speed and no reverse.

### Try delay, then capture a loop

1. Choose a part with a sustained sound or a busy rhythm. Outside extension
   pages, turn STEP off. If its effect send is off, press FUNC, hold **PART >**,
   press that part's pad (1–10), release PART > and turn FUNC off. This toggles
   the send: do it only if you need to turn the send on.
2. Set REVERB MIX near the middle. Open rb.ty, choose **3**, start the sequencer
   and press **pad 2** for a two-step delay.
3. Choose **4** and press **pad 4**. Freeze records four steps starting at the
   next step boundary, then repeats them. Use a sound that continues through
   that window: a short capture between sparse notes can record silence.
4. Try pads **9–12** to change that same fragment. Press transport Stop to
   hear it without the sequencer. Lower MIX to zero and raise it again: the
   fragment is still there.
5. Press **pad 5** to stop the frozen loop.
6. To record another fragment and resume, start the sequencer and press one
   of **pads 1–4**. Speed, reverse and MIX do not restart a pad-5 stop.

### Duration and freeze controls

Pads 1–4 select one, two, three or four straight steps: a sixteenth, eighth,
dotted eighth or quarter note. At 120 BPM these last 125, 250, 375 and 500 ms.
Longer windows reduce the storage sample rate; tempo-change artifacts are part
of the lo-fi effect.

In freeze, pressing any of pads 1–4 requests a new recording at the next
step boundary, even if that duration is already selected. The sequencer needs
to be running for a new capture.

| Freeze pad | Action |
| --- | --- |
| 1–4 | Choose a duration, record a new fragment and resume after a pad-5 stop |
| 5 | Stop the loop and cancel a pending recording; keep program 4 selected |
| 9 | Play the existing fragment at half speed |
| 10 | Play it at normal speed |
| 11 | Play it at double speed |
| 12 | Toggle its playback direction |

Pads 9–12 change the existing fragment, including while the sequencer is
stopped. They do not record another one. Pad 15 lights while a recording is
pending; pad 16 indicates an unavailable clock or capture window. A request
that cannot be carried out leaves the last valid audio state in place.

With freeze, REVERB MIX adds the frozen loop to the direct sound. At zero,
only the direct sound is heard. Turning MIX down does not stop or erase the
recording; raising it brings that same loop back. You can capture at MIX zero.
A note with Time, Echo or Ratchet enters the capture at full send, like the
other notes of a part whose send is on.
Programs 0–3 keep their native MIX/send behaviour.

Transport Stop keeps an active frozen loop playing. Start requests another
capture with the selected controls. A pad-5 stop stays stopped through
Stop/Start, page exit and speed/reverse changes. Resume with a new recording
from pads 1–4. Switching to another program and back to 4 also starts a new
capture; reopening rb.ty does not.

Audio backup clears effect history. Delay resumes empty. An active freeze
needs a new capture with the selected controls; a pad-5 stop remains stopped.

## Song: play memories in a chain

A song plays pattern memories one after another, one pass of the pattern
each, and starts again from the first. For example, positions 1, 2 and 3 with
memory 1 and position 4 with memory 2 play memory 1 three times, memory 2
once, then start over.

Build it on the **SonG** page.

1. Choose the memory to start with, as usual with MEMORY and a pad.
2. Open SonG. With no song the display shows SonG and the pads are dark.
3. Press pad 1. Position 1 takes the memory in use and the display shows, for
   example, `01.03`: position 1, memory 3.
4. Press pad 2 to add position 2 with the same memory, then turn
   SAMPLE/SELECT to choose its memory, 1–10. Add positions the same way, up
   to sixteen.

The lit pads are the positions. A position's pad selects it; the next pad
adds a position with a copy of the last memory; pads further on do nothing,
so the positions always stay in a row. To remove a position, select it and
turn SAMPLE/SELECT below 1: the following positions move back. Removing the
only position ends the song.

When stopped, pad 1 sets up the song at once and Play starts it; while
playing, the song takes over when the current pattern ends. The playing
position blinks. Changes you make while it plays apply from the next position.
Leaving the page keeps the song: SonG is where you arrange it, and you play it
from LIVE and the other pages.

**During a song everything works as with a pattern**: STEP and the notes,
MUTE, PART < and PART >, REC, the knobs and MIDI control changes, the pads,
SAMPLE/SELECT, LIVE with MUTE and MEMORY held, the loop and every extension
page. Edits change the memory in use.

At each new position:

- **The same memory keeps playing** without reloading, as when a pattern
  repeats: your edits, mutes, knob moves, a LIVE effect and the loop carry on.
- **Another memory loads** as MEMORY and a pad would: the running LIVE effect
  ends, and the parts, mutes and knobs are the new memory's. Unsaved edits of
  the memory you leave are lost when it loads again from its saved copy: keep
  them with WRITE and that memory's pad first.
- Bars keep counting through the song, so Predictability and the bar filter
  follow the song's bars, not each memory's.

**Pattern mutes and the loop belong to each memory.** A memory's part mutes
and its loop are what WRITE saved. For example, positions 1–3 have memory 2
and position 4 has memory 4. Mute a part outside LIVE while memory 2 plays:
that pattern mute stays through positions 1–3. Memory 4 arrives with its own
pattern mutes. When memory 2 loads again, it brings its saved mutes; unsaved
changes are gone. The loop follows the same rule.

**Global mutes stay across those changes.** Set them with MUTE held in LIVE
or on **GLob**. They silence the part even when the new memory allows it to
play. WRITE saves the pattern mutes and the loop; it does not save global
mutes.

Save and recall:

- **WRITE + pad 11–16** saves the song in song slot 1–6 and selects it, when
  stopped or while the song plays; playback goes on.
  **MEMORY + pad 11–16** recalls it, at once when stopped, at the end of the
  pattern while playing. These are the Volca Sample's own six song slots:
  songs already saved there are recalled as songs and shown as they are, gaps
  included.
- **WRITE + pad 1–10** saves the pattern in use to that memory, also during a
  song: at once when stopped, at the next step while playing. The song goes on.
- **MEMORY + pad 1–10** loads that memory and ends the song: at once when
  stopped, at the end of the bar while playing.
- Recalling a song turns REC off and leaves STEP as it is.

A save takes a short while. If the song reaches a position with another memory
while a save runs, that position keeps playing the current memory; the
following positions follow the usual rule. The six songs, memory 10 and the
global settings share one area of memory, which every save of a song or of
memory 10 rewrites: as on the standard Volca Sample, do not switch the Volca
off during a save.

Play starts the song from position 1. Stop keeps the position, and the next
Play starts again from position 1. MIDI Continue goes on from where it stopped.

## Patterns and Studio

DataBeat OS 1.1 stores patterns in the LMX6 format. A pattern in another
format does not play, save or take knob edits: convert it first.

Loading a factory pattern gives you an empty pattern. The Volca still has ten
pattern memories. VolcaStudio XL 1.2 rebuilds the Korg factory patterns from
your own Korg 1.42 updater, the file it builds DataBeat OS from, and saves them
as a DataBeat OS 1.1 bank. The updater holds two sets of ten, set 1 and set 2:
choose one, then restore the memories you want from the new bank.

**From DataBeat OS 1.0.** Convert a copy of your bank with VolcaStudio XL before
restoring it. Every step starts with its Echo on spacing A and its Ratchet as
the part, bars 9–16 repeat bars 1–8, and spacing B of each part starts equal to
spacing A, so the converted memories sound as they did. Echo spacings keep their
durations (1/2, 1, 2, 3, 4 and 8 steps become pads 1, 3, 5, 6, 7 and 8). Steps
switched off in a 1.0 pattern stay off, and AStP changes them.

The dotted 1/4 and one-bar spacings of 1.0 have no equivalent in 1.1.
VolcaStudio XL 1.2 lists every part that uses one of them, and you pick a
replacement for each from the eight spacings of the
[Echo table](#echo-add-quieter-hits-after-each-note); Studio proposes none.
Your choice becomes both spacing A and spacing B of that part. Without a choice
for every listed part, that memory is not converted: it stays as it was.
Studio keeps the original bank and saves a new one.

A complete audio backup contains the ten stored pattern memories and a
separate snapshot of the pattern currently in use, including edits you have
not saved with WRITE. A backup can contain memories in different formats;
select the compatible ones. Restoring the current snapshot to a memory requires
an explicit destination. Restoring a bank does not convert its format.

Pattern backups do not contain sample audio, global settings, songs, LIVE
gestures or captured effect audio. Keep your sample library and original backups.
For the app's procedure, see [VolcaStudio XL pattern banks](https://micheledatabeat.github.io/volcastudio-xl-releases/docs/patterns.html).

## Clock and MIDI

When this Volca runs on its own clock and a long vinyl stop or backcue overloads
it, the Volca catches up at once. The steps that fall inside the catch-up stay
silent, and after the brake the pattern is back on its original bar, with no
rushed or added notes. MIDI clock and **SYNC OUT** stay in time with the
pattern, so a machine following this Volca stays with it too.

**Data bytes without a status are ignored.** A MIDI message starts with a
status byte (note on, control change, and so on) followed by its data bytes;
a sender may keep sending data after one status (running status). If the Volca
receives data bytes before any status, for example when it is switched on
while a sequencer is already streaming notes, it ignores them until the next
status byte, as MIDI 1.0 asks, and plays from there. The Korg firmware stored
them past the end of its message buffer and could overwrite memory the panel
uses.

Studio uses MIDI to request an audio pattern backup and, if you choose, to
reset the current edit buffer.
