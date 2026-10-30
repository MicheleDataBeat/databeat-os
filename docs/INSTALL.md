# Install DataBeat OS

For the **first-generation Korg volca sample**. Volca Sample 2 is not supported.

DataBeat OS 1.0 is installed with **VolcaStudio XL**, a free application for
Windows, macOS and Linux. Studio contains no firmware. You download Korg's
official updater yourself; Studio builds DataBeat OS 1.0 from it on your
computer, checks the result and sends it to the Volca through **SYNC IN**.

## 1 · Download VolcaStudio XL

Open the [VolcaStudio XL download page](https://micheledatabeat.github.io/volcastudio-xl-releases/)
and choose the **Browser App** (opens in Google Chrome) or the **Desktop App**.
Both install DataBeat OS the same way.

## 2 · Download the official Korg updater

1. Open Korg's
   [volca sample download page](https://www.korg.com/us/support/download/software/0/370/1475/).
2. Read Korg's software licence agreement shown on that page. Downloading means
   you accept it.
3. Under **System Updater**, download version **1.42**:
   `volcasample_updater_1_42.zip` (about 3.1 MB).
4. Keep the zip as it is. Studio accepts the zip itself or the
   `volcasample_sys_0142.wav` inside it. Do not convert, trim or re-save the WAV.

| File | SHA-256 |
| --- | --- |
| `volcasample_updater_1_42.zip` | `f0df310b8bd43b6367dbd0c54ba75e3db53942087e1a4b1ae049f8f08e1731f3` |
| `volcasample_sys_0142.wav` (inside the zip) | `8fe4f43c333a753d589a4d7eff7859e8fce7155cf54b889f4848d595721a55a9` |

On Linux use `sha256sum FILE`, on macOS `shasum -a 256 FILE`, on Windows
`Get-FileHash FILE -Algorithm SHA256`. Studio checks the WAV for you anyway.

## 3 · Add it to Studio

| App | Where | Action |
| --- | --- | --- |
| Browser App | **Firmware** | **Choose the Korg 1.42 updater…** |
| Desktop App | **04 / Firmware** | **Add Korg 1.42 updater…** |

Studio builds DataBeat OS 1.0 and checks the result: the updater and the built
image must match their pinned SHA-256 values, or nothing is saved. Building
takes a few seconds, needs no internet connection and plays no audio. The
firmware list then shows **DataBeat OS 1.0** and **Korg volca sample 1.42**,
which returns the instrument to Korg's firmware.

## 4 · Install

Use reliable power. Stop other computer audio, including notifications.

1. Select **DataBeat OS 1.0**.
2. Choose the audio output connected directly to the Volca's **SYNC IN**.
   Disconnect speakers and headphones from that output. Disable EQ,
   normalization, crossfade and other audio processing.
3. Power on the Volca while holding **FUNC + PLAY**; the display reads
   **UPdt**. Release the buttons.
4. Start the guided update in Studio with **Begin update…** and confirm. Do not
   interrupt playback or switch off the Volca. The transfer lasts about
   40 seconds.
5. Wait for **End** on the Volca, then power off and on again. At startup the
   display scrolls **dAtAbEAt OS**.

Firmware audio is a data signal: never listen to it through speakers or
headphones. Studio's **Signals sent** means the computer finished playing; only
**End** on the instrument confirms the installation.

## After restarting

- The version check (power on while holding **REC**) can show **1.60**: this is
  the updater header version used by DataBeat OS.
- You do not need to install Korg 1.42 first. Studio only uses Korg's updater
  file to build DataBeat OS.
- Saved samples remain. Installing firmware does not convert stored pattern
  memories.
- To open an extension page: press **FUNC**, turn **SAMPLE/SELECT** to choose
  it, then press **FUNC** again. Use **WRITE** to save a pattern to a memory.

See the [manual](MANUAL.md) for every page and control, and
[Return to Korg firmware](RETURN-TO-KORG.md) to go back.
