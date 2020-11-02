### Objectives

The main goal of this lab is to gain experience with synthesizer modules--the different categories they fall into, and how they chain together to modify an audio signal.

The second goal is to understand the relationship of hardware and software--how software can *represent* hardware, and also how hardware and software can control one another to (arguably) musical ends.

And so, this lab will comprise the following:
- Some history of modular synths
- An introduction to the idealized world of **module types** vs the messy and wonderful world of **module implementations**
- The opportunity to build your own (virtual) modular synth rack using VCV Rack
- The opportunity to (optionally) control your setup with the hardware you've already built.

Your **deliverable** will be a video recording of your custom rack setup making noise (or music?), and a paragraph describing your most interesting discovery during the building process, to be done **before your lab section**.

During lab section, we'll share, discuss, and expand our setups, steal cool ideas our labmates came up with, and make weird and glorious noises.

<br>

### Overview  

Electronic synthesizers were first developed in the 1960s as a way for musicians to create instruments that are not tied to the physical constraints of acoustic instruments. These devices were enabled by newly available (at the time) electronic components and although the implementation of these instruments is dramatically different between the [first Moog](https://www.moogmusic.com/news/early-years-moog-synthesizer) and the Rack software you will explore in this lab, the fundamental pieces remain quite similar.

In the 1970s Modular synthesizers gained popularity due to their flexibility and customizability (foreshadowing the complex effects pedals that are now standard in many rock guitar kits--stay tuned for more next week). The Serge synthesizer that Prof. Tutschku demonstrated in his lecture is one of the first examples of a modular synthesizer, and we can recreate many, if not all, of these features virtually with computer software. Using computer software allows us to expand beyond the limits of electronic implementations, allowing even more "far-out" sounds and musical experiments. Although often there are idiosyncracies of hardware components that software never quite recreates exactly, and so there remains a growing community of hardware synth builders, collectors, and enthusiasts.

[Here's a resource](https://www.synthesizers.com/begin.html) from a purveyor of fine synthesizers that gives a nice overview of the various components of a modular synthesizer.

<br>

### Module Types & Implementations

Happily, you've already gone quite deeply into the idea of module types in [this week's lecture video](https://harvard.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=3b73681d-fb38-42fd-87e5-ac330107e910) with Prof. Hans Tutschku, and also in [Ableton's synth explorable](https://learningsynths.ableton.com/) from Monday's class. You've also already installed and made a some noise with [VCV Rack](https://vcvrack.com/) in last week's MIDI lab, so we're hitting the ground running!

Synths and synth modules come in all shapes and sizes, and tinkerers, designers, engineers, musicians, mad-scientists, and artists the world over have been inventing synths of different shapes, sizes, layouts, and sonic capabilities for over half a century. Thinking in terms of some basic module types, or categories, gives us a reliable way to navigate this ever-changing wilderness. Some such module types we've already discussed in this class are:

- **Oscillators** (sine, square, triangle, sawtooth, LFOs...)
- **Envelopes** (Ampliude modulation: Attack, Decay, Sustain, Release)
- **Filters** (low pass, high pass, band pass...)
- **Effects** (distortion, reverb, compression, delay...)

Our goal now is to expand these categories, and to look at some of the different forms they take in the wild. Do you remember the VCV Rack setup Prof. Hans Tutschku used to improvise at the end of his lecture?

![13](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/13.png)

Woah! How will we begin to make sense of this web of cables and knobs and buttons?! Let's start by taking a look at VCV Rack's **Library Page:**

[https://library.vcvrack.com/](https://library.vcvrack.com/)

From this page, you can explore all the different modules that various people in the VCV Rack community have created. Near the upper right of the page, you'll see a dropdown menu called "Tag" and When you click on it, you'll see the following list:

<img style="max-width: 200px;" src="https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/tags.png" alt="image12" />
<br>

As you glance down this list of tags, you'll see some familiar words, like *Distortion, Effect, Envelope, Filter, MIDI, Oscillator, and Reverb*. Some of these are broad categories (like "*Effect*"), while others are a little more specific (like "*Reverb*", which is a type of effect).

We can use these VCV Rack tags to expand our list of module types. This isn't an exact science, because you might use the same module for different musical purposes. But nonetheless, the tags might fall into groupings as follows:

<br>

To generate and modify signals:

- **Signal Generators**
  - Oscillator, Function Generator, Low-frequency oscillator, Noise, Sampler, Sample and hold
- **Effects**
  - Chorus, Compressor, Expander (opposite of compression), Delay, Distortion, Flanger, Limiter, Phaser, Reverb, Ring modulator, Waveshaper (changes the shape of a waveform)
- **Envelope**
  - Envelope generator, envelope follower
- **Filter**
  - Low-pass gate, Equalizer
- **Pitch Control**
  - Tuner, Slew limiter (often used to create a "slide" between pitches), Quantizer ("quantizes" the frequency spectrum into different scales, etc)

<br>

To trigger and program events:

- **Controller**
- **MIDI**
  - Clock generator, clock modulator
- **Sequencer**
  - Sequencer, Arpeggiator, Random (randomizes events), Logic

<br>

And some broader categories:

- **Audio Routing & Amplitude**
  - Mixer, Switch, Panning, Voltage-controlled amplifier, Attenuator (the opposite of an amplifier), Dynamics (affects the amplitude)
- **Recording**
- **General Descriptors**
  - Digital, Drum, Dual (stereo), Quad, External, Granular, Hardware clone, Multiple, Physical modeling, Polyphonic, Visual
- **Instrument types**
  - Synth voice, Vocoder

<br>

You can also type in a search term and see what kinds of modules turn up. If you find yourself wondering, for example "what the heck is a *slew limiter*?!" here is [a helpful glossary](https://learningmodular.com/glossary/) where you can look it (and any other mysterious synth term) up!

<br>

### Build Your Rack

**Adding Modules**

To add modules to your rack, you will first need to [register](https://vcvrack.com/login) with VCV Rack using an email address and password. This will allow you to link the modules you choose in the Library to your VCV Rack software, so you'll only install the modules you actually want to use! Once you've registered, sign in to your new account from the "Library" menu in the VCV Rack software, and your library preferences and software will be connected.

You can click on any module you find in the VCV Rack Library to go to its info page, which often contains a description of the module, and often links to a detailed manual or external resources. As Prof. Hans Tutschku rightly said, you could spend the rest of the semester--or the rest of your life (!) exploring these modules...

When you find a module you like, you will see an option to **Subscribe** to that module. Subscribing to a module means adding it to the collection of modules you'll use in your rack. Once subscribed, you can select Library > **Update** within the VCV Rack software, and all your subscribed modules will be available for use.

Finally, to place a module in your rack, control+click your rack, and the modules library popup will appear, allowing you to choose the module you want to add. Similarly, to remove a module, control+click the module itself and choose "delete."

**Connecting Modules**

Connecting modules of a modular synth together is called "patching," and in the hardware world, this is done using patch cables. In VCV Rack, you can click and drag between two terminals to create a *virtual* patch cable between two modules. Through patching, you can route your initial signal through all the various modules in your rack, and the final sound is the result of all the different ways your modules have successively modified the initial sound.

**Go for it!**

Building your rack will take a lot of (very fun and noisy) exploration and experimentation.

To make sure you're exploring broadly, see that your final rack includes, at a minimum:
- one module type that generates sound
- three different module types that modify your initial sound
- one module type that triggers events in time, such as a controller, sequencer, or randomizer
- one module from a category that's completely new to you! (what's a waveshaper? or a Vocoder?)

Once you've found a configuration you like, you can save your rack as a `.vcv` file by choosing File > Save As. Saving regularly is always a good idea, so you won't accidentally lose your soniferous work!

<br>

### Hardware Controllers

VCV Rack emulates hardware synthesizers using software, but if you're tired of *everything* being so virtual these days, hardware control brings your virtual rack into the physical world.

You can very easily assign any button, knob, slider, or other part of a virtual Rack module to the hardware controller of your choice. Check out the first minute or so of this video to see how:

<br>
<p><iframe style="width: 640px; height: 480px;" title="Midi Mapping in VCV Rack 1.0" src="https://www.youtube-nocookie.com/embed/Dd0EESJhPZA?start=37;feature=oembed&amp;rel=0" width="640" height="480" allowfullscreen="allowfullscreen" webkitallowfullscreen="webkitallowfullscreen" mozallowfullscreen="mozallowfullscreen" allow="geolocation *; microphone *; camera *; midi *; encrypted-media *; autoplay *"></iframe></p>
<br>

Prof. Hans Tutschku used a controller very much like the one in this video during his improvisation. And as luck would have it, you built your very own Arduino MIDI controller in lab last week! You've even used to control VCV Rack!

Try using the method in the video to assign the buttons of your MIDI controller to different controls on your custom Rack setup. It's also worth noting that the leftmost button in the three-button controller you built last week works as a type of sequencer--it plays a programmed sequence of ascending notes, whereas the middle and right buttons more immediately capture your realtime musical performance.

**Continuous Control**

As incredibly cool as your Arduino MIDI controller is, it has one very significant limitation: it is made entirely of buttons!

Buttons are great for controlling things that are either "on" or "off," but what if you want to control something more variable, like realtime volume, or a filter sweep, or, well, anything that you can't control with a button?!

There are all kinds of electronic components that can give you this kind of control, from gyroscopes and accelerometers (which measure when you tilt or move your hardware) to photo sensors (which measure light levels), and many more. But perhaps the most common such component on synthesizers is the *potentiometer*, which most often takes the form of knobs and slders.

Your lab kit contains potentiometers that look like little blue knobs. This next part is entirely **optional**, but if you'd like to wire one up and give it a try (it only takes mere moments!), here's what to do:

- The potentiometer in your kit has three pins. Connect the left pin to ground, and the right pin to VCC (see the photos below).
- Connect the middle pin to "A1" on the Arduino (this is an "Analog" pin that supports continuous control).
- Download the exacmple Arduino code from the [Lab 9 Folder](https://canvas.harvard.edu/courses/75224/files/folder/Lab%209%20Code) on Canvas and upload the code to your Arduino.

Now, when you press the middle button of your 3-note controller, you can adjust the pitch continuously by turning the potentiometer! 🤯

This is just to spark your imagination about ways you can expand your hardware controller. Take a peek at the Arduino code to see what it's doing, tinker around, and talk with your Lab TF if you think you might want to incorporate some expanded hardware control into your upcoming electronic instrument build!

![potentiometer](https://gened1080.bok.tools/resources/canvas//assignments/Analog-Synths/images/pot.jpeg)
###### The blue potentiometer added to last week's 3-note MIDI controller.

<br>

### Deliverables

1. Once you've built your rack, Choose File > Save As to save it as a `.vcv` file, and upload that file to Canvas.

2. Then, make a short recording of your setup in action. You can do this with a screen recording, or with your phone, or with one of the *Recording* modules within Rack itself, or by another means of your choosing. Upload this recording to Canvas as well.

3. Finally, write a paragraph describing your most interesting discovery while you were building your rack. Perhaps it was a module that behaved differently than you expected it to, or perhaps it was an unexpected sound that emerged from the combination of two or more different modules? This is wide open, and will no doubt lead to some great discussion with your labmates and TF!

<br>

### Some Rack modules to explore

Just to break the ice, here are screenshots of the Rack configurations from lab, and from Prof. Hans Tutschku's lecture. You might start by finding some of the modules used in these setups, and by looking at how they're patched together. This is only a suggestion, so feel free to start off on your own as well!

Default Rack configuration from Lab:

![0](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/0.png)

Configurations Hans used in order:

![1](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/1.png)

![2](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/2.png)

![3](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/3.png)

![4](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/4.png)

![5](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/5.png)

![6](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/6.png)

![8](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/8.png)

![9](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/9.png)

![10](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/10.png)

![11](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/11.png)

![12](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/12.png)

![13](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/13.png)

<br>

### A Final Thought

If, in your musical adventures, you've encountered a piece of music creation software such as:
- GarageBand
- Ableton Live
- Logic
- Fruity Loops
- Pro Tools...

...and many others, these are all examples of "Digital Audio Workstations" (DAWs), and you can understand each of these, also, as collections of modules all working together to musical ends.

For example, GarageBand has a library of built-in instruments, as well as a library of loops, and a way to record music step by step, layer by layer.

The instruments in a program like GarageBand are either synths (made up of a series of oscillators, filters, and so forth), or sample-based instruments (which use an audio recording rather than an oscillator as the initial signal).

The loops are a programmed sequence of events sent to the instruments, and these can, in turn, become a higher level sequence of events, arranged into a song.

In short, you can begin to discover the similarities, and the different design choices in each piece of musical software you use, by applying the same kind of thinking it takes to construct and analyze modular synths.

And while DAWs generally focus on a higher level of abstraction from modular synths, there are also programs that focus even more closely on the details of patching between modular objects. For example, the visual programming languages [Max/MSP](https://cycling74.com/get-started) and [Pure Data](https://puredata.info/) (both invented by the same electronic composer) operate by connecting programmatic objects together using virtual patch cables--just like a synth--but allow you to build your modules from smaller ingredients, as though you were building a circuit.

So adding an effect within a DAW, or adding an effect module to a modular synth, or patching a source to an effects object in code are all different ways of incorporating the same engineering concept into your creative musical process. This applies in the world of hardware as well--like plugging your guitar into an effects pedal--as we will discover in more detail next week!
