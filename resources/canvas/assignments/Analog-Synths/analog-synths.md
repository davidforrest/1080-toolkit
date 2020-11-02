### Objectives

The main goal of this lab is to gain experience with synthesizer modules--the different kinds, and how they chain together to modify an audio signal.

A secondary goal is to understand the relationship of hardware and software--how software can *represent* hardware, and also how hardware and software can control one another to (arguably) musical ends.

And so, this lab will comprise the following:
- Some history of modular synths
- An introduction to the idealized world of **module types** vs the messy and wonderful world of **module implementations**
- The opportunity to build your own (virtual) modular synth rack using VCV Rack (including at least x modules of arguably different types)
- The opportunity to (optionally) control your setup with the hardware you've built.

Your **deliverable** will be a video of your custom rack setup making noise (or music?), and a paragraph describing your most interesting discovery during the process, to be done **before lab section**.

During lab section, we'll share, discuss, and expand our setups, steal cool ideas our labmates came up with, and make weird and glorious noises.

<br>

### Overview  

Electronic synthesizers were first developed in the 1960s as a way for musicians to create instruments that are not tied to the physical constraints of acoustic instruments. These devices were enabled by newly available (at the time) electronic components and although the implementation of these instruments is dramatically different between the [first Moog](https://www.moogmusic.com/news/early-years-moog-synthesizer) and the Rack software you will explore in this lab, the fundamental pieces remain quite similar.

In the 1970s Modular synthesizers gained popularity due to their flexibility and customizability (foreshadowing the complex effects pedals that are now standard in many rock guitar kits). The Serge that Prof. Tutschku demonstrated in his lecture is one of the first examples of a modular synthesizer, and we can recreate many, if not all, of these features with computer software. And using computer software allows us to expand beyond the limits of electronic implementations, allowing even more "far-out" sounds and musical experiments. 

[Here's a resource](https://www.synthesizers.com/begin.html) from a purveyor of fine synthesizers that gives a nice overview of the various components of a modular synthesizer.


### Module Types & Implementations

Happily, you've already gone quite deeply into the idea of module types in [this week's lecture video](https://harvard.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=3b73681d-fb38-42fd-87e5-ac330107e910) with Prof. Hans Tutschku, and also in [Ableton's synth explorable](https://learningsynths.ableton.com/) from Monday's class. You've also already installed and made a little noise with [VCV Rack](https://vcvrack.com/) in last week's MIDI lab. So we're hitting the ground running!

Synths and synth modules come in all shapes and sizes, and tinkerers, designers, engineers, musicians, mad-scientists, and artists the world over have been inventing synths of different shapes, sizes, layouts, and sonic capabilities for more than half a century. Thinking in terms of some basic module types, or categories, gives us a map through this ever-changing wilderness. Some such types we've already discussed are:

- **Oscillators** (sine, square, triangle, sawtooth, LFOs...)
- **Envelopes** (Ampliude modulation: Attack, Decay, Sustain, Release)
- **Filters** (low pass, high pass, band pass...)
- **Effects** (distortion, reverb, compression, delay...)

Our goal now is to extend these categories, and to look at some different forms they take in the wild. Do you remember the VCV Rack setup Prof. Hans Tutschku used to improvise at the end of his lecture?

![13](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/13.png)

Woah! How will we begin to make sense of this web of cables and knobs and buttons? Let's start by taking a look at VCV Rack's **Library Page:**

[https://library.vcvrack.com/](https://library.vcvrack.com/)

From this page, you can explore all the different modules people in the VCV Rack community have created. Near the upper right of the page, you'll see a dropdown menu called "Tag" and When you click on it, you'll see the following list:

<img style="max-width: 200px;" src="https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/tags.png" alt="image12" />

As you glance down this list of tags, you'll start to see some familiar words, like *Distortion, Effect, Envelope, Filter, MIDI, Oscillator, and Reverb*. Some of these are broad categories (like "*Effect*"), and others are a little more specific (like "*Reverb*", which is a type of effect).

We can use this list of VCV Rack tags to expand our model of module types. This isn't an exact science, because you might use the same module for different musical purposes. But nonetheless, an expanded model might look something like this:

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
  - Tuner, Slew limiter (often used to create a "slide" between pitches), Quantizer ("quantizes" the freqency spectrum into different scales, etc)

To trigger and program events:

- **Controller**
- **MIDI**
  - Clock generator, clock modulator
- **Sequencer**
  - Sequencer, Arpeggiator, Random (randomizes events), Logic

Broader use categories:

- **Audio Routing & Amplitude**
  - Mixer, Switch, Panning, Voltage-controlled amplifier, Attenuator (the opposite of an amplifier), Dynamics (affects the amplitude)
- **Recording**
- **General Descriptors**
  - Digital, Drum, Dual (stereo), Quad, External, Granular, Hardware clone, Multiple, Physical modeling, Polyphonic, Visual
- **Instruments**
  - Synth voice, Vocoder

You can also type in a search term and see what kinds of modules turn up. If you find yourself wondering, for example "what the heck is a *slew limiter*?!" [here's a helpful glossary](https://learningmodular.com/glossary/slew-limiter/) where you can look it up!


### Build Your Rack

**Adding Modules**

To add modules to your rack, you will first need to [register](https://vcvrack.com/login) using an email address and password. This will allow you to link the modules you choose in the Library to your VCV Rack software, and only install the modules you want to use! Once you've registered, sign in to your new account from the "Library" menu in VCV Rack, and your library and software will be connected.

You can click on any module you find in the VCV Rack Library to go to its information page, which often contains a summary of the module, and usually also links to a manual or external resources, like the module's source code. As Prof. Hans Tutschku said, you could spend the rest of the semester--or the rest of your life exploring these modules!

When you find a module you like, you will see an option to **Subscribe** to that module. Once subscribed, you can select Library > **Update** within the VCV Rack software, and all your subscribed modules will be available for use.

To add a module, control+click your rack, and the modules library popup will appear. Similarly, to remove a module, control+click the module itself and choose "delete."

**Connecting Modules**

Connecting modules together is called "patching," and modules are connected together using patch cables. In VCV Rack, you can click and drag between two terminals to create a virtual patch cable. Through patching, your initial signal gets routed through all the various modules in your rack, and the final sound is the result of all the different ways your modules have successively modified the initial sound.

**Go for it!**

Building your rack will take a lot of (very fun and noisy) exploration and experimentation.

To make sure you're exploring broadly, make sure that your final rack includes, at a minimum:
- one module that generates sounds
- three different modules that modify your initial sound
- one module that triggers events in time, such as a controller, sequencer, or randomizer
- one module from a category that's completely new to you!

Once you've found a configuration you like, you can save your rack as a `.vcv` file by choosing File > Save As. Saving regularly is always a good idea, so you won't accidentally lose your work!


### Hardware control

VCV Rack emulates hardware synthesizers using software, but we can still control our virtual rack in the physical world.

You can very easily assign any button, knob, slider, or other part of a hardware controller to any control on a virtual Rack module. Check out the first minute or so of this video to see how:

<br>
<p><iframe style="width: 640px; height: 480px;" title="Midi Mapping in VCV Rack 1.0" src="https://www.youtube-nocookie.com/embed/Dd0EESJhPZA?start=37;feature=oembed&amp;rel=0" width="640" height="480" allowfullscreen="allowfullscreen" webkitallowfullscreen="webkitallowfullscreen" mozallowfullscreen="mozallowfullscreen" allow="geolocation *; microphone *; camera *; midi *; encrypted-media *; autoplay *"></iframe></p>
<br>

Prof. Hans Tutschku used a controller very much like the one in this video during his improvisation. And as luck would have it, you built your very own Arduino MIDI controller in lab last week, and you've even used to control VCV Rack!

Try using the method in the video to assign the buttons of your MIDI controller to different controls on your custom Rack setup. It's also worth noting that the leftmost button in the three-button controller you built last week works as a type of sequencer--it plays a programmed sequence of ascending notes, whereas the middle and right buttons more immediately capture your realtime musical performance of individual notes.

**Continuous Control**

As incredibly cool as your MIDI controller is, it has one very significant limitation: it is made entirely of buttons!

Buttons are great for controlling things that are either "on" or "off," but what if you want to control something more variable, like realtime volume, or a filter sweep, or, well, anything that you can't control with a button?

There are all kinds of electronic components that can give you this kind of control, from gyroscopes (which measure when you tilt your hardware) to photo sensors (which measure light), and many more. But perhaps the most common such component on synthesizers is the *potentiometer*, which most often takes the form of knobs and slders.

Your lab kit contains potentiometers that look like little blue knobs.  your If you would like to experiment with adding

![potentiometer](https://gened1080.bok.tools/resources/canvas/assignments/Analog-Synths/images/pot.png)




- buttons vs continuous control



### Deliverables

1. Once you've built your rack, Choose File > Save As to save it as a `.vcv` file, and upload that file to Canvas.

2. Then, make a short recording of your rack in action. You can do this using a screen recording, or with your phone, or with one of the *Recording* modules within Rack itself, or by another means of your choosing. Upload your recording to Canvas as well.

3. Finally, write a paragraph describing your most interesting discovery while you were building your rack. Perhaps it was a module that behaved differently than you expected it to, or perhaps it was an unexpected sound that emerged from the combination of two or more different modules? This is wide open!


### Rack modules to explore

Rounding up staring points, here are screenshots of Rack configurations from Lab and Hans's lecture.

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

### Extra

A final thought about DAWs:
- instruments + sequencers
- some examples

We could (perhaps?) include a live demo of Max during lab, and a brief discussion of some other DAWs, software tools, hardware controllers, and hardware synths to open up this field for the electronic instrument and/or final project.
