# Save Shutdown for Adafruit Power Boost 1000c

This project is a save shutdown for the Adafruit Power Boost 1000c. You can use this circuit to delay the power-off, after the user switched the device off. You can detect that and execute a shutdown on e.g. your Raspberry Pi. The available time depends on the RC-time-constant (current values 1MOhm, 22uF -> 1MOhm * 22uF = 22s). You can try other values with the (lt-)spice simulation in `simualtion/`, depending on your needs. Even though I'm an electrical engineer im not a master in circuit design, which means that there might be a better way to do this (potentially with less electrical components). If you have any suggestions create a pull request or open an issue.

## Usage

The circuit was created with Fritzing (https://fritzing.org/). Download and install it, to edit the files and generate gerber files. If you just use a breadboard, you will be fine with the following preview.

## Preview

#### Breadboard schematic
<img src="img/save_shutdown_breadboard.png" alt="breadboard" width="500">
<br>

#### PCB schematic
<img src="img/save_shutdown_pcb.png" alt="pcb" width="500">
<br>

#### LT-Spice simulation
The shutdown delay is approx. 22s, which matches the RC time contant of (1MOhm * 22uF =) 22s. 

<img src="img/save_shutdown_simulation.png" alt="simulation" width="500">
<br>

#### Oscilloscope waveform
The shutdown delay is approx. 12s with the RC time contant of (1MOhm * 22uF =) 22s. The blue waveform is the second terminal of the switch, the yellow is the 5V output of the Adafruit Power Boost 1000c.

<img src="img/save_shutdown_oscilloscope.bmp" alt="oscilloscope" width="500">
<br>

#### Test circuit
The arrow colors math the waveform colors from the oscilloscope. The red wire is connected to Bat+, black to Bat-. The 1MOhm resistor on the left side of the right picture is used to detect the button switch (here for oscilloscope, but can also be used for e.g. Raspberry Pi GPIO).

<img src="img/save_shutdown_testbench.png" alt="testbench" width="500">

## Dependencies

PowerBoost 1000C Fritzing Component:
* https://github.com/adafruit/Fritzing-Library
* It is included in `lib/`. The folder also includes their `LICENSE.txt`.

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
