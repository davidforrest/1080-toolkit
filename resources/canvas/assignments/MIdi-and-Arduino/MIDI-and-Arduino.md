### Objectives:

1. **Introduction to MIDI** (Music Instrument Digital Interface)

  - Introduce simple input and output circuits for MIDI with an Arduino application
  - Make a simple MIDI instrument with an Arduino
  - Test/play with your electronic instrument and interface with an external MIDI enabled device (for this lab, your computer)
  - **Submission: Short video (15s) of your MIDI instrument in action!**

2. **Expand your instrument** to include additional keys
  - **Submission: Short video (15s) of your 14-note instrument in action!**



### Equipment and components to be used:

- Arduino
- Push buttons
- Wires and breadboard
- Resistors
- MIDI connector and MIDI-USB cable
- Your computer - this will be our audio synthesizer, specifically using “VCV Rack”

### Overview

**MIDI Background**

Prior to 1980, electronic instruments and synthesizers had no standardized control scheme, so components made by different manufacturers were often incompatible and could not communicate. In the early 1980’s, the Musical Instrument Digital Interface (MIDI) protocol was proposed and developed, which allowed for any MIDI electronic instrument or synthesizer to be used as a controller or an output for any other MIDI-compatible device.

Rather than storing and transmitting the raw audio data (for which file sizes are typically quite large), MIDI data is a set of “instructions” describing the input, such as “note on/off,” “pitch,” or “velocity of the note.” While MIDI is not sending actual audio signals, the MIDI set of instructions contain enough information to recreate music on another device. With these instructions, devices like computers or microcontrollers (like your Arduino MKRZero) could be used to control electronic instruments like keyboards or drum kits, or one instrument could serve as the input for a different instrument.  

MIDI messages take up far less space (sometimes up to 1,000 times smaller than the corresponding audio) and up to 16 channels can be directed at once. Since its introduction, MIDI has been adopted widely, initially by record producers and professionals, and later became far more widespread with the introduction of the personal computer into video games, home recording setups, and music education. Today, we’ll be exploring both MIDI-in and MIDI-out circuitry in combination with your Arduino keyboards and a MIDI-compatible synthesizer.

While in our previous lab we input signals to the microcontroller (via buttons) and generated output signals from the microcontroller (that controlled an LED and speaker), in this lab we’ll see how we can input signals to a microcontroller, transfer the corresponding coded sound information via MIDI protocol, and then synthesize the sound by interpreting the MIDI information.

**Before you start**

In this lab, we will be wiring up a MIDI instrument to transmit what sounds we want played (our “instrument”). The MIDI instrument functions as a MIDI-OUT that will send MIDI data. This MIDI data will then be transferred via a MIDI cable to our software synthesizer, which receives and understands the MIDI data (our “synthesizer” - MIDI-IN) and will play the sounds that were sent!

In our setup, the Arduino MKRZero and buttons function as the MIDI instrument. The Arduino MKRZero generates MIDI commands that are sent through the MIDI-USB cable into a port on your computer. These MIDI commands are then interpreted by the VCV Rack software to synthesize sound!

![image15](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image15.png)

**IMPORTANT!** Do NOT plug the USB MIDI cable or Arduino into your computer at this point!

## Part 1: (wiring up the circuit)

We recommend using a new breadboard if possible for this part of the lab, as you will be expanding your keyboard from last week’s lab in part 3 of this week’s lab. Simply disconnect the Arduino MKRZero from last week’s lab, as well as any wires that might be connected to it, but leave everything else intact (including the buttons, speaker, LED, and resistors) so you can use it for your final electronic project build if so desired.

Follow the circuit building instructions carefully and check with your TF when finishing wiring for double/triple check for potential any shorts/etc.

1. Wire up the circuit as shown in Fig1 for the **MIDI instrument**:

NOTE: The diagram below shows the MIDI connector jack facing toward you, HOWEVER, in your circuit, it should be facing away from you! This allows us to easily make connections between the breadboard and the three relevant pins on the back of the MIDI connector. You can see the correct configuration in the circuit photos that follow.

![image2](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image2.png)
##### Fig. 1: Midi Instrument (MIDI OUT - Transmits/sends MIDI Data).

Connect the VCC and GND connections from the MKRZero to the bottom red and blue rails of the breadboard, respectively. For this lab, be sure to orient your breadboard so the topmost rail on the top row is blue, and the bottom most row on the bottom row is red. This will allow us to more easily make the connections for the MIDI connector.

Correct orientation:
![image8](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image8.png)

Incorrect orientation:
![image7](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image7.png)

Wire up three push buttons as we did in lab 7. The pulldown resistor values should all be 10K Ohm (brown-black-orange). Connect the three push buttons to the digital pins D1, D6, and D7 on the Arduino, respectively.

![image1](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image1.png)

![image6](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image6.png)

![image21](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image21.png)

For the MIDI connector, place it in the breadboard so the jack faces away from you. Notice that there is a row of five pins (slightly offset from one another), and a row of two pins. The row of two pins should be connected to the top ground (blue) rail, and the other five pins should be connected to five separate rows on the breadboard.

- With the MIDI jack facing away from you, the second-from-the-left pin (counting from the left in the pictures below) of the MIDI connector should connect to a 33 Ohm (orange-orange-black) resistor, which then connects to the positive (VCC, 3.3V) rail of the breadboard.
- The middle pin of the MIDI connector should connect to ground.
- The second-from-the-right pin (or the 4th pin from left) of the MIDI connector should connect to a 10 Ohm (brown-black-black) resistor, which then connects to pin 14 (also labelled as “TX” here) of the Arduino.
- Finally, jump the ground rail from the bottom of the breadboard to the top of the breadboard. This grounds the two pins of the MIDI connector to prevent noise from interfering with the MIDI codes being sent.

![image17](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image17.png)

![image4](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image4.png)

![image13](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image13.png)

Double check the wiring to make sure everything is correct (especially for the MIDI connector!)  Ask your TF to check **before** plugging the Arduino into your computer or the USB MIDI cable into your computer.

## Part 2: (Programming the microcontroller)

Use the Arduino Library Manager (Sketch > Include Library > Manage Libraries) to install the MIDI library. Search for “MIDI I/Os for Arduino” (with Type set to “Contributed” and Topic set to “Communication”) and select the library named “MIDI Library”, as pictured below. Use the current install version, 5.0.2 (it should already be selected in the dropdown menu).

![image11](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image11.png)

- Code files are on Canvas, under the folder [Lab 8 Code](https://canvas.harvard.edu/courses/75224/files/folder/Lab%208%20Code)
- Connect your Arduino MKRZero to your computer and upload the provided code.
- Close the Arduino IDE, and disconnect the Arduino board.

## Part 3A: (Install Rack and set up your Audio Output)

We need software on your computer to read and interpret the MIDI commands that you are generating from your Arduino instrument. To use Rack as the MIDI synthesizer, we’ll first need to install the Rack software. Then we’ll configure the port on our computer to be able to receive MIDI commands.

1. Install Rack on your computer.

First, download the installer from VCVRack: [https://vcvrack.com/Rack](https://vcvrack.com/Rack).

Next, follow the install instructions for your operating system: [https://vcvrack.com/manual/Installing](https://vcvrack.com/manual/Installing).

**Windows** Install Instructions
- Run the installer.


**MacOS** Install Instructions
- Download, unzip, and copy the Rack app to your Applications folder.

**Linux** Install Instructions
- We recommend instead installing [ZynAddSubFX](https://zynaddsubfx.sourceforge.io/download.html), as it has better support for Linux.   

2. Set up audio:

Just to make sure Rack is working, we’re going to try making some sound using your computer’s keyboard as a MIDI controller.

Open up Rack.

In the MIDI-CV module, click the 1st line and select Computer keyboard, and click on the 2nd line and select QWERTY keyboard:

![image14](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image14.png)

Then, in the AUDIO-8 module, click the 1st line and select your computer’s audio driver, and click on the 2nd line and select your computer audio device that is active/in-use:

**Windows:**  
![image12](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image12.png)

**Mac:**  
![image16](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image16.png)

**Linux:**  
![image3](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image3.png)

ou can keep the default settings for all the other Rack modules for now.

Now press “z x c v b” on your computer keyboard – you should hear something like “Do Re Mi Fa So.” If you do, great, your Rack software works!  If you don’t hear anything – troubleshoot!

## Part 3B: (configure your MIDI Input)

**After getting approval from your TF**, plug your MIDI instrument into your computer and power it on via USB. Note that you’ll need two USB ports – one to power the arduino which we’ve already programmed, the other for the USB MIDI cable.

- Connect the “IN” end of the USB MIDI cable (included in the kit)  to the MIDI jack of the MIDI circuit you just built.
- Make sure the “OUT” end of the MIDI-USB cable is not connected to anything.
- Connect the USB MIDI cable (the USB end)  to your computer.
- Connect your Arduino to your computer via USB.

![image9](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image9.png)

Once you’re all plugged in, launch Rack, and configure VCV Rack to use the MIDI device you just built (instead of your computer’s keyboard) as an input device:

**For Windows:**

In the MIDI-CV module, choose Windows MIDI, USB MIDI Interface (this will have a number corresponding to your device), and MIDI Channels: All channels

![image22](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image22.png)

**For Mac:**

In the MIDI-CV module, choose Core MIDI, USB MIDI Interface (this will have a number corresponding to your device), and MIDI Channels: All channels

![image19](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image19.png)

**For Linux:**

On a Linux system, the port should already be recognized natively. To check that the port is recognized after you’ve connected the USB-MIDI cable to your computer, open a terminal and run `lsusb`, which should return a device “USB MIDI Interface”. If it doesn’t, try running `sudo chmod 777 /dev/bus/usb/001/075`

Additionally, you can see when MIDI commands are being issued by the Arduino by running  `aseqdump -p 20` while pressing buttons to issue MIDI commands with the Arduino (after you’ve flashed the Arduino firmware above). You should see commands like the following, which indicates that the Arduino is emitting MIDI commands correctly:

![image18](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image18.png)

Open up Rack, and update the MIDI-CV settings so that , “**ALSA**” (on **Linux**) is the MIDI driver, and “USB MIDI Interface” is the MIDI device. You can keep the MIDI Channel as “**All Channels**”.

![image20](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image20.png)

**Make some music!**

Now, you should be able to press the push buttons on your breadboard and hear sound being played by the audio synthesizer! You should notice the LED on the MIDI-USB connector blinking when MIDI commands are being transmitted, and the yellow LED on the MKRZero should also remain lit while MIDI commands are being transmitted.

For debugging purposes, if the yellow light on your MKRZero turns on but the MIDI-USB light doesn’t flash / you hear no sound, there is probably an issue with how you’ve wired up your MIDI connector OR an issue with how your computer is interpreting the MIDI command. Let us know if you have any problems with this part!

**Press button 1**
- What do you hear?
- Where does it come from?
- What do you see?

**Press button 2**
- What do you hear?
- Where does it come from?
- What do you see?

**Press button 3**
- What do you hear?
- Where does it come from?
- What do you see?

If it works as designed/expected, great! You’ve just finished the MIDI part of Lab 8.
If not, troubleshoot/debug, figure out why, and retest. Feel free to ask for help from your TF, or collaborate with others on Slack to see if you can figure out what’s wrong!

**Submission for the MIDI part of this lab: Short video (15s) of your MIDI instrument in action!**

## Part 4: (Electronic Piano Build)

Now return to work on the electronic piano, using the concepts you learned about buttons, switches, and resistors in circuits from the last lab. Below is an example wiring for the Arduino synth (music plays out of the breadboard speaker):

![image10](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image10.png)

![image5](https://gened1080.bok.tools/resources/canvas/assignments/MIDI-and-Arduino/images/image5.png)

**Electronic Piano**

Build an electronic piano using the components provided and skills you gained in the previous lab. Your piano should cover at least 14 notes and light up an LED each time a note is played.

Some things to think about:

- Consider **how you can use the buttons** that we’ve made in this lab to make a piano with more keys. Do you see now why we’ve demonstrated how to use both the analog and digital inputs on the arduino, given the number of notes you need?
- How do you think you would **modify your code** to work well with many notes rather than just two? You could copy and paste for each individual note, but a more elegant solution may be possible that lets you reuse the code that remains the same for each note

Hint: we have included an updated code sketch that you can feel free to use, in the “Lab 8 Code” folder on Canvas.

- If you build the 14-key Arduino synthesizer, which would use your physical speaker from Lab 7, be sure to use the Arduino sketch `lab8_arduino_synth_14keys.ino`. The speaker should now be connected to digital pin 7, and the buttons should be connected to the analog pins A0-A6, and D0-D6 (14 pins on the arduino in total).
- If you instead build the Arduino 14-key Arduino instrument and use the software synthesizer introduced in this week’s lab, be sure to use the Arduino sketch `lab8_arduino_instrument_14keys.ino`. The buttons should be connected to the analog pins A0-A6, and D0-D6 (14 pins on the arduino in total).

**Keep your breadboarding and code neat and organized!** We’ve given you some guidelines on how to wire up your Arduino in the past couple labs, as well as some suggested wire colors (for example, always use red for the supply voltage, black for ground, etc.)

- While there are in theory many places you could place components on the breadboard with any colored/sized wires that would still work, with larger circuits you will want to be able to visually debug and sort through what you’re looking at, so keep it organized.
- The same goes for code -- be sure to save a separate copy before you begin modifying things, and leave comments throughout so that you can tell what your code does.

**Submission for the Electric Piano part of this lab: Short video (15s) of your 14-note instrument in action!**

Take a short video of you playing your synthesizer (feel free to play a few notes, a fun tune that you enjoy, or even try to recreate your acoustic composition!) and upload to Canvas!
