# RE-Tape-Echo

**RE-Tape Echo is an attempt to recreate my own Roland RE-150 Space Echo in Pure Data for Critter and Guitari's Organelle.**

**Featuring :**
* original controls on the first page : 6 echo modes, repeat rate, intensity, echo volume
* two play heads with a fixed delay ratio of 1 to 3
* bypass
* two individual gain controls

**Imperfections :**
* a repeat rate-dependent filter as a tape/head simulation
* motor speed fluctuations
* input bleed to echo
* bad erasing head

**Fun stuff :**
* 10 presets state saving system
* tap tempo and fine tempo control (1 and 0.1bpm steps)
* 4 routing modes
* o-knob enabled : see https://github.com/bapch/o-knob

### TODO
* rename "tape loop amount" to "tape loop"
* add a sound-on-sound option
* rename Single and Repeat modes to Repeat and Single :o)

### v1.2 changes :
* presets now are actually saved across reboots and reloads… don’t laugh.
* thresholding has been modified to allow an easier and consistent reach of extreme pot values

### v1.1 changes :
* move to o-knob library v2 : it’s much easier to dial parameters…

_If you want to transfer your saved presets, open v1 and v1.1 on your computer. Enter the [pd presets] subpatch of v1. The big message boxes at the bottom are your presets. Copy the content of each message box to the corresponding message box in v1.1_

### Manual
1. Parameters and pages
   1. Page one : original controls
      * Mode : Single or Repeat. The two modes are inverted on my unit and i dumbly replicated this... So the Single mode has feedback, and the Repeat mode has none.
      * Repeat rate : change the delay length
      * Intensity : feedback amount
      * Echo volume : wet volume
   2. Page two : motor speed fluctuations
      * Wow : low frequency fluctuations
      * Flutter : mid frequency fluctuations
      * Dirt : high frequency fluctuations
   3. Page three : more imperfections
      * Input bleed : Bleed from the input to the echo signal. Subtle
      * Tape loop : simulate a real length of tape loop. If overdriven, the sound won't be completely erased from the tape and you'll hear it on the next turn.
      * Playhead filter : The tape and the playhead are not perfect and filter the sound depending on the tape speed. Low repeat rate = less highs, high repeat rate = better highs, high-pass filter at 130Hz, modelled on my RE-150. You can choose to disable this filter and get a very clean echo.
   4. Page four : useful stuff
      * gainL : Sets the gain of the left input from 0 to 2 (-60dB to +6)
      * gainR : Sets the gain of the right input from 0 to 2 (-60dB to +6)
      * i/o modes : sets the routing
          * 1 + 2 to echo to LR
          * 1 to echo to L, 2 to R
          * 2 to echo to R, 1 to L
          * 1+2 to echo to R, 1+2 to L
   5. Page five : save/load
      * operation : select save or load
      * preset : select the preset to save or to load
      * apply : turn from all the way to the left to all the way to the right to apply
 
2. Pots and Keyboard

RE-Tape Echo has many parameters, the Organelle has few pots. That's why one pot controls several parameters, depending on the page you are on. In order to prevent any parameter jump, you have to move the pot to its displayed value to start changing the parameter. This is also true for the "apply" pot from the 5th page, although you don't see its value... I'm working on it.

* Use the Aux button to browse through the pages
* First C (60) : tap tempo. Tap twice to set the tempo. The led turns white on the first tap and red again on the second
* Notes C# (61) and D (62) respectively nudge the tempo by 1 and -1 BPM
* Notes D# (63) and E (64) respectively nudge the tempo by 0.1 and -0.1 BPM
* Last B (83) : toggles bypass tails-style. The led flashes red when fx is ON and yellow when it's in BYPASS

