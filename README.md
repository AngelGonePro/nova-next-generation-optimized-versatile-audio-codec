# NOVA - Next-generation Optimized Versatile Audio
This codec made 7.1 audio from FLAC, WavPack 5.9.0, and APE 13.x to 100MB vs the 102MB from APE which is the best compression codec currently out.
As of right now all ran inside of a `index.html` please note loading a `.nova` file may take a while for you to get the option to playback the file.
This is a prototype of possibly a new lossless codec for storage conscious users.
If anyone is willing to expand on this or wants a better lossless codec and can code feel free to take inspiration or fork it and make it better.
The world need something better for once instead of keeping the same old outdated things.

## `index.html` is the encoder!

`player.html` is a player for this custom codec!

---

NOVA achieves approximately 2.23:1 lossless compression on a 7.1, 24-bit, 48 kHz track at 3 minutes and 18 seconds.
"Decoded audio is bit-for-bit identical to the source WAV."
<br>
NOVA currently approaches or exceeds APE-level compression in my initial tests. On the tested 7.1 material, NOVA produced a smaller file than APE. On the tested stereo material, APE's maximum compression setting produced the smallest file, with NOVA only ~0.2 MB larger while remaining smaller than FLAC. All NOVA results were bit-perfect.
<br>
Initial testing shows NOVA achieving compression competitive with Monkey's Audio (APE). APE currently produces smaller files on the tested stereo material, while NOVA has produced a smaller file than APE on the tested 7.1 material and smaller files than FLAC on some stereo material. All NOVA tests shown have passed bit-exact lossless verification.
<br>
"Preliminary testing suggests NOVA may have particularly strong compression characteristics with multichannel audio. On a 6:32 24-bit/48 kHz Hotel California 7.1 track, NOVA produced a 193.6 MB file compared with 200.6 MB for Monkey's Audio and 261.4 MB for FLAC, while passing bit-exact verification."

---

## Test it for yourself:
Albums in Test file:
- Bach — Goldberg Variations — Nicholas Angelich
- Vivaldi — The Four Seasons — London Philharmonic / Itzhak Perlman
<br>

Takes a while to Decode but when you have a playlist its gapless :q
<br>

Made sure to use non copyrighted audio btw.
<br>

user: Guest
<br>

Pass: GuestAccount
<br>

NextCloud Link: https://cdntest.cosmoscraft.net/index.php/s/nfSGQJTLfgj8ArB
<br>

Website, from `nova-web-player.zip`: https://music.cosmoscraft.net/web.html DISCLAIMER: Firefox decoding is not the best and you may want an entire song to finish decoding before playback.

## NOVA is an experimental lossless audio codec designed to achieve better compression than existing lossless codecs while preserving bit-perfect audio and metadata.
## Development status: NOVA is currently an experimental proof-of-concept. The initial implementation was created with AI-assisted development and is intended primarily to demonstrate the concept. Contributions from developers experienced in audio compression, DSP, entropy coding, C/C++, Rust, SIMD, or multimedia formats are welcome.

## Detailed Compression Comparison

> All NOVA results shown below passed bit-exact round-trip verification.
> APE was tested at Extra High because it produced smaller files than
> Insane in the tested material. FLAC was tested at compression level 8.
>
> For the Chemical comparison, the APE and FLAC files were encoded from
> the same 24-bit / 48 kHz source used for the 24-bit NOVA test. The
> original 32-bit WAV was converted to 24-bit / 48 kHz before FLAC/APE
> comparison.
>
> Therefore, the 32-bit NOVA Chemical result is shown separately as an
> implementation/diagnostic test and is not used as a direct APE/FLAC
> comparison.

| Song / Test | Audio Type | Channels | Bit Depth | Sample Rate | Duration | Raw PCM | Codec | Compression Setting | File Size | NOVA Ratio vs PCM | Space Saved | Bit-Exact |
|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---|
| **Hotel California** | Stereo | 2 | 24-bit | 48 kHz | 6:32 | 107.74 MB | WAV | Uncompressed | 110,462 KB | 100% | 0% | — |
| | | | | | | | **APE** | **Extra High** | **76,771 KB** | — | — | — |
| | | | | | | | **FLAC** | **Level 8** | **78,276 KB** | — | — | — |
| | | | | | | | **NOVA** | Current prototype | **79,138 KB** | **71.7%** | **28.3%** | **PASS** |
| **Hotel California** | 7.1 | 8 | 24-bit | 48 kHz | 6:32 | 430.95 MB | WAV | Uncompressed | 441,428 KB | 100% | 0% | — |
| | | | | | | | **APE** | **Extra High** | **200,583 KB** | — | — | — |
| | | | | | | | **FLAC** | **Level 8** | **261,354 KB** | — | — | — |
| | | | | | | | **NOVA** | Current prototype | **193,629 KB** | **43.9%** | **56.1%** | **PASS** |
| **Chemical — Post Malone** | 8-channel / Atmos bed | 8 | **24-bit** | 48 kHz | 3:02 | 200.27 MB | WAV | Uncompressed | — | 100% | 0% | — |
| | | | | | | | **FLAC** | **Level 8** | **85,542 KB** | — | — | — |
| | | | | | | | **APE** | **Extra High** | **84,147 KB** | — | — | — |
| | | | | | | | **NOVA** | Current prototype | **82,002 KB** | **40.0%** | **60.0%** | **PASS** |
| **Unforgettable — French Montana** | Stereo | 2 | 24-bit | 48 kHz | 3:51 | 63.49 MB | WAV | Uncompressed | 65,162 KB | 100% | 0% | — |
| | | | | | | | **APE** | **Extra High** | **44,097 KB** | — | — | — |
| | | | | | | | **FLAC** | **Level 8** | **45,327 KB** | — | — | — |
| | | | | | | | **NOVA** | Current prototype | **44,822 KB** | **68.9%** | **31.1%** | **PASS** |

## Codec Configuration

| Codec | Compression Setting | Purpose |
|---|---|---|
| **NOVA** | Current prototype | Experimental codec |
| **Monkey's Audio (APE)** | **Extra High** | Smallest APE result observed in testing |
| **FLAC** | **Level 8** | Maximum FLAC compression |
| **WAV** | Uncompressed PCM | Source/reference |

> **APE note:** APE was tested at multiple compression levels. 
> "Extra High" produced smaller files than "Insane" in the tested
> material, so Extra High is used for the comparisons shown here.

## Preliminary Observations

These results are experimental and do not represent NOVA's final
compression performance.

- NOVA has successfully produced bit-exact lossless reconstructions
  for all tested files.
- On the tested 7.1 Hotel California material, NOVA produced a smaller
  file than both APE and FLAC.
- On the tested stereo material, NOVA is competitive with APE and FLAC,
  but does not consistently beat them.
- NOVA shows substantially different compression behavior depending on
  the source material and bit depth.
- A particularly significant difference was observed when testing the
  same Chemical multichannel material at 32-bit and 24-bit depth.
- The 32-bit Chemical test produced a 173.44 MB NOVA file from
  273.66 MB of raw PCM (63.4%).
- The 24-bit Chemical test produced an 80.08 MB NOVA file from
  200.27 MB of raw PCM (40.0%).
- In the 32-bit test, the raw extra-bits payload was 167.30 MB,
  compared with only 63.79 MB in the 24-bit test.
- This suggests that the current NOVA implementation may have a
  significant inefficiency in its 32-bit sample/residual handling.
- Further investigation is required to determine whether the cause is
  predictor precision, residual representation, extra-bit handling,
  entropy coding, or another aspect of the 32-bit encoding path.

## Known Investigation: 32-bit PCM Compression

Preliminary testing indicates that NOVA's current implementation
compresses 32-bit PCM significantly less efficiently than equivalent
24-bit material.

This is currently under investigation.

Example:

| Source | NOVA Ratio | Raw Extra-Bits |
|---|---:|---:|
| Chemical 8ch 32-bit | 63.4% | 167.30 MB |
| Chemical 8ch 24-bit | **40.0%** | **63.79 MB** |

The 24-bit version also produces a larger rANS payload, suggesting that
more of the signal is reaching the entropy-coding stage rather than
being stored through the raw extra-bits path.

This may represent a significant optimization opportunity.

## Images:

![alt text](https://github.com/AngelGonePro/nova-next-generation-optimized-versatile-audio-codec/blob/main/media/Screenshot%202026-08-25%20100347.png)
![alt text](https://github.com/AngelGonePro/nova-next-generation-optimized-versatile-audio-codec/blob/main/media/Screenshot%202026-08-25%20100354.png)
![alt text](https://github.com/AngelGonePro/nova-next-generation-optimized-versatile-audio-codec/blob/main/media/Screenshot%202026-08-25%20124934.png)
![alt text](https://github.com/AngelGonePro/nova-next-generation-optimized-versatile-audio-codec/blob/main/media/Screenshot%202026-08-25%20125508.png)

| Area                                 | Current status  |
| ------------------------------------ | --------------- |
| Working proof of concept             | 🟢              |
| Actual audio test                    | 🟢              |
| 7.1 demonstration                    | 🟢              |
| Comparison codecs                    | 🟢              |
| Size measurements                    | 🟢              |
| Timing measurements/screenshots      | 🟢              |
| Playback demonstration               | 🟢              |
| Clear experimental status            | 🟢              |
| Ready for developer outreach         | **🟢 Yes**      |
| Production-ready codec               | 🔴 No           |
| Formal codec specification           | 🟡 Later        |
| Large benchmark corpus               | 🟡 Later        |
| Optimized native implementation      | 🟡 Later        |
| Community/contributor infrastructure | 🟡 Worth adding |
