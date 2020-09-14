### Objectives

- Construct and manipulate a CAD (computer-aided design) model
- Optional: 3D print your CAD file

<br>

### General Overview

We’ve all seen acoustic horns in the form of musical instruments and megaphones -- but how do they work?

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image14.png" />
###### [Acoustic horn patent, 1944](https://patents.google.com/patent/US2338262A/en)

<br>

Essentially, a horn is an acoustic waveguide (a device that makes sound wave propagation more efficiently) by limiting energy loss. While we perceive horns to “amplify” the sound source, but what is actually happening is that the horn makes the sound transfer more efficient. It does so by a concept called **impedance matching**.

**Acoustic impedance** is how much something *impedes*, or resists, the transfer of acoustic energy. If we have a narrow opening, the impedance is high, which restricts the flow of waves (sound, electricity, water etc). A wide opening, on the other hand, would have a low impedance, since it is easier for these waves to flow. Impedance also depends on the properties of a material, like its stiffness and density.

When we speak, for example, there is a huge **impedance mismatch** between our throat to the open air. Our throat is a narrow pipe that is made of materials that are higher in density and stiffness relative to the surrounding air, which is not stiff or dense at all. Adding in a horn made of a stiff material, however, helps to ease the transition, making the acoustic wave transfer more efficient. The end close to the sound source is now “denser” than the open end of the horn, and the horn shape gradually changes the impedance. To summarize, **acoustic horns make sound travel more efficiently due to impedance matching.**

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image2.png" />
<br><br>
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image15.png" />

###### Image source: [Why You Hear What You Hear, Chapter 7](https://www.whyyouhearwhatyouhear.com/subpages/chapter7.html)

<br>

### Lab Overview

This lab will introduce you to designing acoustic instruments. One could still draw out plans and designs on a blueprint, but that method is tedious and hard to realize into three dimensional shapes.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image18.png" />

<br>

Computer Aided Design (CAD) programs make this part of the design process much easier (once you know the software). There is a large range of CAD programs from kid-friendly usability to software used to design space shuttles.

In this lab, we will learn the basics of computer aided design. There will be a walk-through of how to design a parabolic horn from scratch. The follow-up to the lab will be to design a flute mouthpiece with given dimensions, which will be 3D printed and shipped in your kit.

<br>

## Equipment and Components

- Computer with Fusion360 installed
- Computer mouse (optional, but will make your life easier)

<br>

## The Procedure

<br>

### Part 1: Installing CAD software

**1. Install Autodesk Fusion360 on your computer.** It is a CAD program that is free for students and can be downloaded [here](https://www.autodesk.com/products/fusion-360).

- If for some reason you cannot download the software or do not have a computer that can handle it, follow the instructions below to use the virtual machine.
- Optional: If you have never used Fusion360 or other CAD programs, here's a [Video Introduction to Fusion360](https://www.youtube.com/watch?v=NbqjegtMUgU&).

<br>

**2. If you need to use Fusion360 on a virtual machine:**

- Go to Canvas and click on “FAS OnDemand” in the left hand navigation pane.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image23.png" />

- Launch the virtual machine called “Windows Solidworks”. If you uncheck the box that says “Start from a new copy of image” you won’t have to install Fusion360 each time you launch it. However, don’t rely on saving your work on the virtual machine since it may give you a fresh copy if it can’t launch your previous one for some reason.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image19.png" />

- When your virtual machine is ready , click on the link to launch it. Fusion360 is not installed by default and you will have to install the software as if you were installing it on your own computer.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image25.png" />

<br>

### Part 2: Exponential horn

This section is to get you familiar with Fusion360 and some of the basic functions of computer aided design. For this exercise, we will be creating a parabolic horn (bell) for the end of the flute that will be created next week. I HIGHLY recommend that you save after each step. [Here](https://youtu.be/lq5rM2Z88KE) is a video tutorial for this section.

<br>

**1. Basics of using Fusion360**

- See image below for a brief overview of the overall interface and most relevant icons. This is also reviewed in the video linked above:

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image5.png" />

<br>

**2. Check/change the units to millimeters** by clicking on your name in the upper  right corner-> Preferences -> Default Units -> Design -> Default units for new design.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image17.png" />

<br>

**3.** Make sure you’re in “DESIGN” mode (top left) and click the “Sketch” button (first icon in the “CREATE” section. Then select any of the planes . Note the orientation in the 3D plane view in the top right of the screen.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image7.png" />

<br>

**4.** Since we’re looking at making a bell shape, we will be using the REVOLVE feature. For inputs to create the shape, we need an axis to revolve around and a profile. The first thing we’ll draw is an axis. To do that, select the LINE tool and in the SKETCH PALLETTE that pops up, click on the button to the right of where it says “Construction” so it is blue. Then click on the ORIGIN (where the little circle icon is on your screen) and then click somewhere above it. You want this line to be vertical and it should snap to it when you get close. When you’re done, press escape to get out of the LINE tool but don’t exit out of the sketch.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image9.png" />

<br>

**5.** Now we’re going to draw the profile. For this we will use the dimensions below:

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image8.png" />

<br>

**6.** To draw this, let’s start with the line tool again. You can start with any of the three lines, but to make it easier, we’ll start with the one going vertically. Click on the blue construction symbol in the sketch palette to stop drawing construction lines. Click on the origin again and then drag the line vertically the same way you made the construction line. The dimensions don’t matter yet, so when you get it to a decent length click the mouse. Without exiting the line tool, you can then turn 90 degrees and click again when the line is horizontal and looks similar to the picture above. When you have that, press escape to exit the line tool then click on the line tool again and create the bottom line.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image20.png" />

<br>

**7.** None of these have been dimensioned but that’s ok, we can dimension them afterwards. Go under CREATE and click on “Sketch Dimension”. Click on the line you want to add a dimension, drag the dimension to where you want it to be, and then type the number. Do that for the other two lines. Avoid dimensioning the construction line instead of the solid lines.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image31.png" />

<br>

**8.** We now need to make the exponential curve that makes this an exponential horn. Click on CREATE->Conic Curve. Select the point at the end of the bottom line, then the point at the end of the top line, and then click somewhere close to the middle. When prompted for a value, type in 0.5 and hit enter. You can then dimension the location of this point by using the Sketch Dimension feature and clicking on the point and the bottom line for the vertical dimension and the point and the left line for the horizontal dimension.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image16.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image12.png" />

<br>

**9.** When you’re done with the profile and have dimensioned it, click on the “FINISH SKETCH” button in the upper right.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image35.png" />

<br>

**10.** Now we need to make this into a three dimensional shape. Click on the REVOLVE icon at the top. In the REVOLVE window, click the box next to “Profile” and select the shape you drew. It should then display “1 selected”. Then click on the box next to “Axis” and click on the construction line you drew. Then click OK.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image3.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image10.png" />

<br>

**11.** We now want to hollow out the shape. We could have drawn the hollowed out shape within the profile, but for this lab we will use the SHELL tool. Click on the SHELL tool and then click on the top and the bottom faces of the bell. It should state “2 selected” to the right of faces/body. For “Inside Thickness” type 3.00 mm and you want the direction to be “Inside”. Click OK when you’re done.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image26.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image32.png" />

<br>

**12.** Finally we want to create a groove that will allow you to assemble this to the other flute pieces. Click on SKETCH and select the top face of the bell. Use the “Center Diameter Circle” tool and then click on the center point of the bell and stretch the circle outward. Dimension the circle to 18.7mm and then click FINISH SKETCH.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image30.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image33.png" />

<br>

**13.** Click on your new profile and then click on EXTRUDE. In the EDIT FEATURE box, set the Distance to 3.8mm and the operation should be “Join”. The arrow should also be pointing away from the bell and if it isn’t, you can drag it to the correct side.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image24.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image13.png" />

<br>

**14.** Congrats! You have made a CAD part. The next section will test your skills and have you work on a more complex part. Make sure you save your part!

<br>

### Part 3: Whistle mouthpiece

This next section is to get you to play with more of the features and build off of what you just learned. It won’t be as directed as Part 2, but if you get stuck, feel free to ask questions in Slack. Remember to save often and you can always use the undo button.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image4.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image1.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image34.png" />

**1.** Start with creating a solid cylinder that is 25.4mm in diameter by 100 mm long (hint, just a circle sketch that is extruded).

**2.** Create the mouth cutout by sketching an arch on the midplane of the cylinder. You’ll need to use the “Cut” feature in the extrude box and cut in both directions.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image11.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image6.png" />

<br>

**3.** Hollow out the side opposite of where your mouth goes by cutting a circle with a diameter of 14mm to a length of 50mm.

<br>

**4.** Cut out the hole you blow in using the dimensions below. For getting the rectangle in the right location, you can create a construction circle the same way you made a construction line and then have the two points at the bottom of the rectangle COINCIDENT (there’s a button for that) to the circle to ensure it is centered. Also, there’s a rectangle tool so you don’t have to draw four lines. Cut the hole “To Object” and select the circular face inside the mouthpiece (where your previous cut ended).

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image21.png" />

<br>

**5.** Cut out the fipple hole (the part that makes the air to vibrate) using the sketch below. Cut it from the center and go in both directions for a half length of 5mm.

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image22.png" />

<br>

**6.** Remove the extra material by cutting from the inside of the mouthpiece and cutting to a length of 20mm:

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image28.png" />

<br>

**7.** Cut the ridge so the PVC pipe fits by cutting a circle with a diameter of 21.5mm to a depth of 4mm.

<br>

**8.** Cut a ridge so the other flute pieces fit  with a diameter of 18.8mm and a depth of 4mm.

<br>

**9.** Round the edges of the mouthpiece with a fillet:

<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image29.png" />
<img src="https://gened1080.bok.tools/resources/canvas/assignments/Prototyping%20I/images/image27.png" />

<br>

**10. CONGRATS!** You’re done. If your kit has arrived, compare your CAD with the physical pieces.

<br>

## Deliverables

**1.** Upload the CAD files to Canvas.
