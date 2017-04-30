# RE-Tape-Echo

** RE-Tape Echo is an attempt to recreate my own Roland RE-150 Space Echo in Pure Data for Critter and Guitari's Organelle.**

**Featuring :**
* original controls on the first page : 6 echo modes, repeat rate, intensity, echo volume
* two play heads with a fixed delay ratio of 1 to 3
* bypass
* two individual gain controls

**Imperfections :**
* a repeat rate-dependent filter as a tape simulation : low repeat rate = less highs, high repeat rate = better highs, high-pass filter at 130Hz, modelled on my RE-150
* motor speed fluctuations : wow, flutter, dirt
* input bleed to echo
* bad erasing head

**Fun stuff :**
* 10 presets state saving system
* tap tempo and fine tempo control (1 and 0.1bpm steps)
* 4 routing modes :
  * 1 + 2 to echo to LR
  * 1 to echo to L, 2 to R
  * 2 to echo to R, 1 to L
  * 1+2 to echo to R, 1+2 to L
* o-knob enabled

### v1.1 changes :
* move to o-knob library v2 : it’s much easier to dial parameters…

_If you want to transfer your saved presets, open v1 and v1.1 on your computer. Enter the [pd presets] subpatch of v1. The big message boxes at the bottom are your presets. Copy the content of each message box to the corresponding message box in v1.1_
