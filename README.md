# NOVA — Next-generation Optimized Versatile Audio Codec

Experimental lossless audio codec focused on efficient PCM compression, with particularly promising results on multichannel audio.

`index.html` is the encoder.
<br>
`player.html` is a local player.
<br>
`Pterdactyl-Web-Ui` folder is a Web ui to play from NextCloud links from any supported web browser.

<br>

If you wanna test:

<br>

user: Guest

<br>

Pass: GuestAccount

<br>

NextCloud Link: https://cdntest.cosmoscraft.net/index.php/s/nfSGQJTLfgj8ArB

<br>

Wen Link: https://music.cosmoscraft.net/web.html

ALL NOVA TESTS BELOW PASSED BIT-EXACT VERIFICATION.


## COMPRESSION COMPARISON

Codec settings:
  NOVA = High Compression
  FLAC = Level 8 (maximum compression)
  APE  = Extra High
  Source = 24-bit / 48 kHz for the main apples-to-apples tests

APE Extra High was used because it produced a smaller file than APE
Insane in testing.

```
+---------------------------+-----+--------+-------+-------+-----------+----------+----------+-------------+-------------+
| Song                      | Ch. | Depth  | Rate  | Time  | Raw PCM   | NOVA     | NOVA %   | APE Extra   | FLAC Level 8|
+---------------------------+-----+--------+-------+-------+-----------+----------+----------+-------------+-------------+
| Hotel California          | 2   | 24-bit | 48kHz | 6:32  | 107.74 MB | 78,069 KB| 70.8%    | 76,771 KB   | 78,267 KB   |
| Unforgettable             | 2   | 24-bit | 48kHz | 3:51  | 63.49 MB  | 44,822 KB| 68.9%    | 44,097 KB   | 45,327 KB   |
| Hotel California          | 8   | 24-bit | 48kHz | 6:32  | 430.95 MB |193,629 KB| 43.9%    |200,583 KB   |261,354 KB   |
| Is There Someone Else?    | 8   | 24-bit | 48kHz | 3:18  | 218.57 MB | 99,034 KB| 44.2%    |105,013 KB   |135,109 KB   |
| Chemical                  | 8   | 24-bit | 48kHz | 3:02  | 200.27 MB | 81,012 KB| 39.5%    | 83,498 KB   | 84,954 KB   |
+---------------------------+-----+--------+-------+-------+-----------+----------+----------+-------------+-------------+
```

---

# FILE SIZE GRAPH — LOWER IS BETTER


## HOTEL CALIFORNIA — STEREO

```
APE   76,771 KB
NOVA  78,069 KB
FLAC  78,267 KB
```

## UNFORGETTABLE — STEREO

```
APE   44,097 KB
NOVA  44,822 KB
FLAC  45,327 KB
```

## HOTEL CALIFORNIA — 7.1

```
NOVA 193,629 KB
APE  200,583 KB
FLAC 261,354 KB
```

## IS THERE SOMEONE ELSE? — 7.1

```
NOVA  99,034 KB
APE  105,013 KB
FLAC 135,109 KB
```

## CHEMICAL — 8 CHANNEL / 24-BIT

```
NOVA  81,012 KB
APE   83,498 KB
FLAC  84,954 KB
```

---

# COMPRESSION RATIO GRAPH — LOWER IS BETTER

```
                         NOVA       APE        FLAC
Hotel California 2ch     70.8%     ~71.2%     ~72.7%
Unforgettable 2ch        68.9%     ~69.5%     ~71.4%
Hotel California 7.1     43.9%     ~46.6%     ~60.6%
Is There Someone Else    44.2%     ~48.1%     ~61.8%
Chemical 8ch             39.5%     ~41.7%     ~42.4%
```

---

# WINNER GRAPH

```
Hotel California — Stereo       APE  > NOVA > FLAC
Unforgettable — Stereo          APE  > NOVA > FLAC
Hotel California — 7.1          NOVA > APE  > FLAC
Is There Someone Else? — 7.1   NOVA > APE  > FLAC
Chemical — 8ch / 24-bit         NOVA > APE  > FLAC
```

# CURRENT SCORE

```
NOVA : ██████████████████████████████████████████████  3 / 5
APE  : ██████████████████████████████                  2 / 5
FLAC :                                                 0 / 5
```

---

# NOVA STORAGE REDUCTION VS RAW PCM

```
+---------------------------+-----------+-----------+
| Song                      | NOVA %    | Saved     |
+---------------------------+-----------+-----------+
| Hotel California Stereo   | 70.8%     | 29.2%     |
| Unforgettable Stereo      | 68.9%     | 31.1%     |
| Hotel California 7.1      | 43.9%     | 56.1%     |
| Is There Someone Else 7.1 | 44.2%     | 55.8%     |
| Chemical 8ch              | 39.5%     | 60.5%     |
+---------------------------+-----------+-----------+
```

# STORAGE SAVED

```
Hotel California — Stereo
29.2% |█████████████████████████████

Unforgettable — Stereo
31.1% |███████████████████████████████

Hotel California — 7.1
56.1% |████████████████████████████████████████████████████

Is There Someone Else? — 7.1
55.8% |███████████████████████████████████████████████████

Chemical — 8ch
60.5% |████████████████████████████████████████████████████████
```

---

# STEREO VS MULTICHANNEL

```
+----------------+-------+----------------------+----------------------+
| Content        | Tests | Average NOVA Ratio   | Average Saved        |
+----------------+-------+----------------------+----------------------+
| Stereo         | 2     | 69.85%               | 30.15%               |
| Multichannel   | 3     | 42.53%               | 57.47%               |
+----------------+-------+----------------------+----------------------+
```
# Average ratio:

```
STEREO
69.85% |██████████████████████████████████████████████████████████████████████

MULTICHANNEL
42.53% |██████████████████████████████████████████
```

---

# DETAILED TEST DATA

```
HOTEL CALIFORNIA — EAGLES — STEREO

Artist:       Eagles
Album:        Hotel California (2013 Remaster)
Track:        Hotel California
Genre:        Rock
Channels:     2
Bit Depth:    24-bit
Sample Rate:  48 kHz
Duration:     6:32

Raw PCM:      107.74 MB
NOVA:         78,069 KB
NOVA Ratio:   70.8%
APE:          76,771 KB
FLAC:         78,267 KB
Verification: BIT-EXACT PASS

NOVA vs APE:
NOVA is 1,298 KB larger.

NOVA vs FLAC:
NOVA is 198 KB smaller.

Result:
APE > NOVA > FLAC


UNFORGETTABLE — FRENCH MONTANA — STEREO

Artist:       French Montana
Album:        Jungle Rules
Track:        Unforgettable
Genre:        Hip-Hop / Dancehall
Channels:     2
Bit Depth:    24-bit
Sample Rate:  48 kHz
Duration:     3:51

Raw PCM:      63.49 MB
NOVA:         44,822 KB
NOVA Ratio:   68.9%
APE:          44,097 KB
FLAC:         45,327 KB
Verification: BIT-EXACT PASS

NOVA vs APE:
NOVA is 725 KB larger.

NOVA vs FLAC:
NOVA is 505 KB smaller.

Result:
APE > NOVA > FLAC


HOTEL CALIFORNIA — EAGLES — 7.1

Artist:       Eagles
Album:        Hotel California (2013 Remaster)
Track:        Hotel California
Channels:     8
Layout:       7.1
Bit Depth:    24-bit
Sample Rate:  48 kHz
Duration:     6:32

Raw PCM:      430.95 MB
NOVA:         193,629 KB
NOVA Ratio:   43.9%
APE:          200,583 KB
FLAC:         261,354 KB
Verification: BIT-EXACT PASS

NOVA rANS payload:
27.54 MB

NOVA raw extra-bits payload:
161.02 MB

NOVA vs APE:
NOVA is 6,954 KB smaller.

NOVA vs FLAC:
NOVA is 67,725 KB smaller.

Result:
NOVA > APE > FLAC


IS THERE SOMEONE ELSE? — THE WEEKND — 7.1

Artist:       The Weeknd
Album:        Dawn FM
Track:        Is There Someone Else?
Genre:        Synth-pop / Synthwave / Contemporary R&B
Channels:     8
Layout:       7.1
Bit Depth:    24-bit
Sample Rate:  48 kHz
Duration:     3:18

Raw PCM:      218.57 MB
NOVA:         99,034 KB
NOVA Ratio:   44.2%
APE:          105,013 KB
FLAC:         135,109 KB
Verification: BIT-EXACT PASS

NOVA rANS payload:
13.88 MB

NOVA raw extra-bits payload:
82.53 MB

NOVA vs APE:
NOVA is 5,979 KB smaller.

NOVA vs FLAC:
NOVA is 36,075 KB smaller.

Result:
NOVA > APE > FLAC


CHEMICAL — POST MALONE — 8 CHANNEL / 24-BIT

Artist:       Post Malone
Track:        Chemical
Channels:     8
Bit Depth:    24-bit
Sample Rate:  48 kHz
Duration:     3:02

Raw PCM:      200.27 MB
NOVA:         81,012 KB
NOVA Ratio:   39.5%
APE:          83,498 KB
FLAC:         84,954 KB
Verification: BIT-EXACT PASS

NOVA rANS payload:
15.66 MB

NOVA raw extra-bits payload:
63.14 MB

NOVA vs APE:
NOVA is 2,486 KB smaller.

NOVA vs FLAC:
NOVA is 3,942 KB smaller.

Result:
NOVA > APE > FLAC
```

---

# CHEMICAL — PREVIOUS 32-BIT TEST

A separate Chemical test used the original 32-bit / 48 kHz / 8-channel WAV.

```
Duration:             3:06
Channels:             8
Bit Depth:            32-bit
Sample Rate:          48 kHz
Raw PCM:              273.66 MB
NOVA:                 173.44 MB
NOVA Ratio:           63.4%
Storage Saved:        36.6%
Verification:         BIT-EXACT PASS
rANS payload:         6.11 MB
Raw extra-bits:       167.30 MB

```
## IMPORTANT:
<br>
This 32-bit result is NOT an apples-to-apples comparison with the
APE and FLAC Chemical results.
<br>
The APE and FLAC comparison files were made from a 24-bit / 48 kHz
FLAC converted from the original 32-bit WAV.
<br>
Therefore the 32-bit NOVA result should be treated as a separate
technical test rather than a codec-vs-codec benchmark.
<br>
The corrected 24-bit Chemical test is the result used in the main
comparison above.

---

# HIGH COMPRESSION MODE

```
High Compression is intended primarily for archival storage.

Compared with the previous NOVA compression mode:

Stereo:
  Approximately 2% smaller
  Approximately 5× slower encode/decode

Multichannel:
  Approximately 1–1.5% smaller
  Approximately 3.5× slower encode/decode

The browser implementation currently decodes JavaScript on a single
thread, so High Compression may cause stuttering or dropouts during
real-time browser playback on slower systems.

The trade-off is intentional:

MORE COMPRESSION
        ↓
SMALLER ARCHIVAL FILES
        ↓
MORE CPU TIME
```


# BIT-PERFECT LOSSLESS VERIFICATION


NOVA is LOSSLESS.
<br>
The benchmark does not judge audio quality using subjective listening
tests.
<br>
Instead, NOVA decodes the compressed file and compares the resulting
PCM data against the original source.
<br>
Result:
<br>
BIT-EXACT ROUND TRIP: PASS
<br>
The decoded audio is bit-for-bit identical to the source WAV.
<br>
Therefore NOVA does not sacrifice audio information to achieve the
compression shown in these tests.

---

# CURRENT FINDINGS


1. NOVA currently wins 3 of the 5 tested comparisons.

2. NOVA wins all 3 tested multichannel comparisons.

3. APE Extra High wins both tested stereo comparisons.

4. NOVA is smaller than FLAC Level 8 in all 5 current tests.

5. The stereo tests place NOVA relatively close to APE.

6. The multichannel tests show a substantially larger NOVA advantage.

7. The current best result is Chemical at 8 channels / 24-bit:
      NOVA = 81,012 KB
      APE  = 83,498 KB
      FLAC = 84,954 KB
      NOVA ratio = 39.5%
      Storage saved = 60.5%

8. The current multichannel average is:
      NOVA ratio = 42.53%
      Storage saved = 57.47%

9. The current stereo average is:
      NOVA ratio = 69.85%
      Storage saved = 30.15%

10. The difference strongly suggests that NOVA's current compression
    architecture may be particularly effective on multichannel audio.

---

# PROJECT STATUS


NOVA is currently an experimental codec and benchmark project.
<br>
The current results are encouraging, especially for multichannel
lossless audio.
<br>
The most important next step is expanding the benchmark dataset and
profiling NOVA's prediction, channel decorrelation, residual, and
entropy-coding stages to determine exactly why multichannel material
currently compresses so effectively.
<br>
The goal is not merely to produce a codec that works, but to determine
whether NOVA can become a practical, open, bit-perfect lossless audio
format with competitive compression, reasonable decoding performance,
metadata support, and broad playback compatibility.

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
