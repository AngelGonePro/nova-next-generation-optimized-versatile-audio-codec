# NOVA - Next-generation Optimized Versatile Audio
This codec made 7.1 audio from FLAC, WavPack 5.9.0, and APE 13.x to 100MB vs the 102MB from APE which is the best compression codec currently out besides this one now.
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

| Codec          |        7.1 source             |      Result |
| -------------- | ----------------------------: | ----------: |
| FLAC           |       ~Recording              |     ~136 MB |
| WavPack        |       ~136 MB FLAC            |     ~105 MB |
| Monkey's Audio |     ~136 MB FLAC              |     ~102 MB |
| **NOVA**       | Needs to be converted to .WAV | **~100 MB** |

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
