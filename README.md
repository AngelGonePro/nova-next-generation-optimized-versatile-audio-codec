# NOVA - Next-generation Optimized Versatile Audio
This codec made 7.1 audio from FLAC, WavPack 5.9.0, and APE 13.x to 100MB vs the 102MB from APE which is the best compression codec currently out besides this one now.
As of right now all ran inside of a `index.html` please note loading a `.nova` file may take a while for you to get the option to playback the file.
This is a prototype of possibly a new lossless codec for storage conscious users.
If anyone is willing to expand on this or wants a better lossless codec and can code feel free to take inspiration or fork it and make it better.
The world need something better for once instead of keeping the same old outdated things.
- Disclaimer: This was Vibe Coded

`player.html` is a player for this custom codec!

## NOVA is an experimental lossless audio codec designed to achieve better compression than existing lossless codecs while preserving bit-perfect audio and metadata.
## NOVA is currently an experimental proof-of-concept. The current implementation is intended to demonstrate the compression concept and is not yet production-ready. Contributions from developers with experience in audio codecs, DSP, compression, C/C++, Rust, SIMD, or multimedia formats are especially welcome.

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
