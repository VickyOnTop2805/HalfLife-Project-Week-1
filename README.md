<div align="center">

<h1>Starbie - My First PCB Project</h1>

<p><strong>Hack Club Half Life | Week 1 - PCB Design</strong></p>

<p>
  My first attempt at designing a custom circuit board,
  learning electronics, and figuring out KiCad along the way.
</p>

<p>
  <img src="https://img.shields.io/badge/Project-PCB%20Design-blue" alt="PCB Design">
  <img src="https://img.shields.io/badge/Software-KiCad%2010-green" alt="KiCad 10">
  <img src="https://img.shields.io/badge/Status-Design%20Complete-orange" alt="Design Complete">
</p>

</div>

<hr>

<h2>About the Project</h2>

<p>
Starbie is my first PCB design project, which I made for Hack Club
Half Life Week 1. The idea is to create a small digital pet that
can interact with people through buttons, sensors and an OLED display.
</p>

<p>
Before starting this project, I had some basic coding knowledge,
but I had never designed a PCB before. I didn't understand how
KiCad worked, what footprints were, or how a schematic could be
turned into an actual circuit board.
</p>

<p>
I decided to follow the Starbie starter project because it seemed
like a good way to learn electronics without needing physical parts
straight away.
</p>

<p>
I used KiCad 10 on my Mac to create the schematic, arrange the PCB,
route the copper tracks, add a ground plane and export the
manufacturing files.
</p>

<p>
This project was definitely more complicated than I expected.
There were several times when I got confused about what I was
doing, but I kept going and eventually managed to complete the
main PCB design.
</p>

<p>
The physical device hasn't been built yet. This repository
documents the PCB design stage and everything I learned.
</p>

<hr>

<h2>Why I Chose Starbie</h2>

<p>
I wanted to make something more interesting than a basic circuit
with an LED that turns on and off.
</p>

<p>
A digital pet sounded interesting because it combines different
electronic components into one project.
</p>

<p>
Starbie could eventually show different expressions, react to
movement, respond to button presses and display information
about its surroundings.
</p>

<p>
I also liked that I could start with a PCB design and later
turn it into an actual physical device.
</p>

<p>
Since I had never used KiCad before, following the starter
guide seemed like a reasonable way to learn.
</p>

<hr>

<h2>Project Goals</h2>

<ul>
  <li>Learn how KiCad works.</li>
  <li>Understand schematic symbols and PCB footprints.</li>
  <li>Create a circuit using the XIAO ESP32-C3.</li>
  <li>Add two physical buttons.</li>
  <li>Connect an OLED display.</li>
  <li>Include a motion sensor.</li>
  <li>Include a temperature and humidity sensor.</li>
  <li>Learn how to route copper tracks.</li>
  <li>Add a ground copper zone.</li>
  <li>Understand PCB design-rule checking.</li>
  <li>Export Gerber and drill files.</li>
  <li>Create a bill of materials.</li>
  <li>Document everything on GitHub.</li>
</ul>

<hr>

<h2>Components</h2>

<table>
  <tr>
    <th>Component</th>
    <th>Quantity</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <td>Seeed Studio XIAO ESP32-C3</td>
    <td>1</td>
    <td>Main microcontroller</td>
  </tr>
  <tr>
    <td>0.96-inch OLED Display</td>
    <td>1</td>
    <td>Displays Starbie's face and animations</td>
  </tr>
  <tr>
    <td>MPU6050 Motion Sensor</td>
    <td>1</td>
    <td>Detects movement and tilting</td>
  </tr>
  <tr>
    <td>DHT11 Sensor</td>
    <td>1</td>
    <td>Measures temperature and humidity</td>
  </tr>
  <tr>
    <td>Push Buttons</td>
    <td>2</td>
    <td>Controls Starbie's interactions</td>
  </tr>
  <tr>
    <td>10k Ohm Resistor</td>
    <td>1</td>
    <td>DHT11 data pull-up resistor</td>
  </tr>
  <tr>
    <td>4-pin Header</td>
    <td>1</td>
    <td>OLED connection</td>
  </tr>
  <tr>
    <td>8-pin Header</td>
    <td>1</td>
    <td>MPU6050 connection</td>
  </tr>
  <tr>
    <td>Custom 2-layer PCB</td>
    <td>1 design</td>
    <td>Connects all the components</td>
  </tr>
</table>

<h3>XIAO ESP32-C3</h3>

<p>
The XIAO ESP32-C3 is the main controller for Starbie.
It will eventually run the code that controls the sensors,
buttons and OLED display.
</p>

<p>
One of the first things I had to learn was how to identify
its different pins.
</p>

<p>
Initially, labels like GND, VBUS, 3V3_OUT, D1, D2 and D3
were confusing because I wasn't familiar with how
microcontroller pins worked.
</p>

<p>
I learned that each pin has a particular function and that
connecting the wrong pins can cause serious problems.
</p>

<h3>OLED Display</h3>

<p>
The OLED screen will act as Starbie's face.
My plan is to display different expressions and animations.
</p>

<p>
I added a four-pin connector for the OLED.
It uses I2C communication through SDA and SCL.
</p>

<p>
I learned that SDA carries data while SCL provides
the clock signal for communication.
</p>

<h3>MPU6050 Motion Sensor</h3>

<p>
The MPU6050 can measure acceleration and angular motion.
I included it so Starbie can eventually react when someone
tilts or shakes the device.
</p>

<p>
It also uses I2C, which means it can share the SDA and SCL
communication lines with the OLED.
</p>

<h3>DHT11 Sensor</h3>

<p>
The DHT11 measures temperature and humidity.
I added it because I wanted Starbie to react to its
environment rather than only button presses.
</p>

<p>
I also added a 10k ohm pull-up resistor to the data line.
This helped me learn why some digital signals need
pull-up resistors.
</p>

<h3>Push Buttons</h3>

<p>
I added two push buttons to control Starbie.
They are connected to the ESP32's GPIO pins and ground.
</p>

<p>
I plan to use the buttons to change expressions,
switch modes or interact with Starbie.
</p>

<hr>

<h2>Software and Tools</h2>

<h3>KiCad 10</h3>

<p>
KiCad was the main software I used for this project.
I used it for:
</p>

<ul>
  <li>Creating the schematic</li>
  <li>Importing custom libraries</li>
  <li>Assigning footprints</li>
  <li>Arranging PCB components</li>
  <li>Routing tracks</li>
  <li>Adding the ground plane</li>
  <li>Running electrical and design-rule checks</li>
  <li>Exporting Gerber and drill files</li>
</ul>

<p>
The interface was overwhelming at first because there
were so many menus, tools and layers.
</p>

<p>
After spending time using it, I gradually started understanding
how the different editors worked together.
</p>

<h3>GitHub</h3>

<p>
I used GitHub to store my project files, bill of materials,
journal and documentation.
</p>

<h3>Hack Club Lapse</h3>

<p>
I used Lapse to record my PCB design process.
It helped me document my actual working sessions
and show how the project developed.
</p>

<hr>

<h2>My Design Process</h2>

<h3>1. Creating the Project</h3>

<p>
I started by installing KiCad 10 on my Mac and
creating a project called Starbie-PCB.
</p>

<p>
At first, I even had trouble creating a new project
because I didn't understand the template selection window.
</p>

<p>
Once I got past that, I opened the Schematic Editor
and started working on the circuit.
</p>

<h3>2. Importing the Custom Libraries</h3>

<p>
The Starbie care package contained symbols, footprints
and 3D models for the components.
</p>

<p>
I initially didn't understand what these files were
or how to import them into KiCad.
</p>

<p>
I had trouble with KiCad's library tables and had
to configure the project-specific libraries.
</p>

<p>
This was one of my first major challenges.
</p>

<p>
Eventually, I managed to import the XIAO ESP32-C3 symbol
and footprint.
</p>

<h3>3. Creating the Schematic</h3>

<p>
After importing the libraries, I started creating the schematic.
</p>

<p>
I placed the XIAO ESP32-C3 first, followed by the power
and ground symbols.
</p>

<p>
I then added two push buttons, the OLED connector,
the MPU6050 connector, the DHT11 sensor and a resistor.
</p>

<p>
I connected the components according to their
intended GPIO and communication signals.
</p>

<p>
One thing I learned was that it's important to
check the actual pin names instead of assuming
a connection is correct just because the wire
looks like it's connected.
</p>

<hr>

<h2>My First Major Mistake</h2>

<p>
One of the biggest mistakes I made was accidentally
connecting the 3.3V power line to GND.
</p>

<p>
At the time, I was still learning how KiCad's wiring
tool worked.
</p>

<p>
The connection points were close together, and I
connected the power wire to the wrong pin.
</p>

<p>
After looking at the schematic more carefully,
I realised the mistake and removed the incorrect wire.
</p>

<p>
I then connected the 3.3V symbol to the correct pin.
</p>

<p>
This taught me how important it is to check
the electrical connections carefully.
</p>

<p>
It was also a reminder that even a tiny mistake
in a schematic can become a much bigger problem
if the physical PCB is manufactured.
</p>

<hr>

<h2>Understanding Footprints</h2>

<p>
This was probably one of the most confusing parts
of the project.
</p>

<p>
When I opened the footprint assignment window,
I saw a huge list of libraries and component names.
</p>

<p>
I didn't understand why I needed footprints when
I had already placed the components in the schematic.
</p>

<p>
I eventually learned the difference:
</p>

<ul>
  <li>
    A schematic symbol represents the electrical
    connections of a component.
  </li>
  <li>
    A PCB footprint represents its physical pads
    and dimensions.
  </li>
</ul>

<p>
I assigned footprints to all the components,
including the ESP32-C3, buttons, connectors,
resistor and DHT11.
</p>

<p>
I also learned that the actual parts need to
match the footprints before manufacturing.
</p>

<hr>

<h2>Moving to the PCB Editor</h2>

<p>
After completing the schematic, I transferred
the components into PCB Editor.
</p>

<p>
At first, everything appeared grouped together
with thin lines connecting different pads.
</p>

<p>
I learned that these lines are called ratsnest lines.
They show the electrical connections that still
need to be routed.
</p>

<p>
I arranged the components around the board,
keeping the XIAO ESP32-C3 near the centre.
</p>

<p>
I placed the buttons toward one side,
the OLED connector near the top and the
other components around the remaining space.
</p>

<p>
I moved and rotated components several times
before settling on a layout.
</p>

<p>
I also had to think about the USB connector
and making sure it would be accessible.
</p>

<hr>

<h2>Routing the PCB</h2>

<p>
Routing was another completely new experience.
</p>

<p>
I learned that copper tracks connect the
different components electrically.
</p>

<p>
I used KiCad's routing tool to connect
the pads based on the schematic.
</p>

<p>
At first, I wasn't sure how to turn corners
or avoid crossing other tracks.
</p>

<p>
As I continued working, I became more
comfortable with the routing tool.
</p>

<p>
I learned that component placement can make
routing easier or harder.
</p>

<p>
After completing the routing, KiCad showed
zero unrouted connections.
</p>

<p>
This was one of the best moments of the
project because I could finally see
the completed circuit board layout.
</p>

<hr>

<h2>Adding the Ground Plane</h2>

<p>
After routing the PCB, I added a ground
copper zone on the B.Cu layer.
</p>

<p>
Before this project, I didn't really
understand what a ground plane was.
</p>

<p>
I learned that a copper-filled area can
provide a shared ground connection
across the board.
</p>

<p>
I selected the back copper layer,
created a zone assigned to GND,
drew its boundary and filled it.
</p>

<p>
At first, the settings were confusing
because there were options for clearance,
minimum width and thermal reliefs.
</p>

<p>
Eventually, I got the copper zone filled
and could see the back copper area.
</p>

<hr>

<h2>Design Rule Checking</h2>

<p>
After routing the PCB, I used KiCad's
Design Rules Checker, also called DRC.
</p>

<p>
The first check reported 19 warnings.
</p>

<p>
Initially, I was worried that I had
made a lot of mistakes.
</p>

<p>
After looking through the warnings,
I realised that most of them involved
silkscreen graphics on the XIAO footprint.
</p>

<p>
Some graphics overlapped solder-mask openings
around the pads.
</p>

<p>
I investigated the warnings and modified
the footprint graphics.
</p>

<p>
After making the changes, I reduced
the warning count from 19 to one.
</p>

<h3>Latest DRC Results</h3>

<table>
  <tr>
    <th>Check</th>
    <th>Result</th>
  </tr>
  <tr>
    <td>Errors</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Warnings</td>
    <td>1</td>
  </tr>
  <tr>
    <td>Unconnected Items</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Schematic Parity Issues</td>
    <td>0</td>
  </tr>
</table>

<p>
The remaining warning says that the XIAO
footprint on the PCB differs from the
library version.
</p>

<p>
I believe this is related to the silkscreen
changes I made, but I still need to verify
the footprint dimensions and pad numbering
before manufacturing.
</p>

<p>
Getting zero errors and zero unrouted
connections was a major milestone for me.
</p>

<hr>

<h2>Exporting the Gerber Files</h2>

<p>
Once the design was routed, I exported
the manufacturing files.
</p>

<p>
I learned that PCB manufacturers use
Gerber files to understand the
different layers of the board.
</p>

<p>
These files describe things like:
</p>

<ul>
  <li>Front copper</li>
  <li>Back copper</li>
  <li>Front solder mask</li>
  <li>Back solder mask</li>
  <li>Silkscreen</li>
  <li>Board outline</li>
</ul>

<p>
I also generated the drill files,
which describe the holes in the PCB.
</p>

<p>
After exporting everything, I opened
the files using KiCad's Gerber Viewer.
</p>

<p>
At first, the different coloured layers
overlapping each other were confusing.
</p>

<p>
I figured out how to hide individual
layers so I could inspect them separately.
</p>

<p>
I checked the copper tracks, pads,
drill holes and board outline.
</p>

<p>
This helped me understand how PCB designs
are prepared for manufacturing.
</p>

<hr>

<h2>Bill of Materials</h2>

<p>
I also created a bill of materials,
usually called a BOM.
</p>

<p>
The BOM lists the parts needed to
assemble the physical Starbie.
</p>

<p>
I searched for suppliers and compared
prices for the components.
</p>

<p>
My original parts list was more expensive,
so I looked for cheaper options.
</p>

<p>
One example was finding a lower-priced
XIAO ESP32-C3 from Seeed Studio.
</p>

<p>
I learned that the lowest component price
doesn't always mean the lowest total cost.
</p>

<p>
Shipping, taxes and minimum order
quantities also matter.
</p>

<p>
The BOM is an initial purchasing plan.
I still need to verify shipping and
component compatibility.
</p>

<hr>

<h2>Problems I Encountered</h2>

<details>
<summary><strong>Problem 1 - Library Setup</strong></summary>

<p>
I had trouble getting KiCad to recognise
the custom symbol and footprint libraries.
</p>

<p>
I learned how project-specific libraries
work and how to configure their file paths.
</p>

</details>

<details>
<summary><strong>Problem 2 - Footprint Assignment</strong></summary>

<p>
I didn't initially understand the difference
between symbols and footprints.
</p>

<p>
After learning what each one represents,
I was able to assign the footprints
to the components.
</p>

</details>

<details>
<summary><strong>Problem 3 - Incorrect Power Connection</strong></summary>

<p>
I accidentally connected 3.3V to GND.
</p>

<p>
I removed the incorrect connection
and rewired the schematic.
</p>

</details>

<details>
<summary><strong>Problem 4 - PCB Routing</strong></summary>

<p>
I initially found it difficult to route
tracks without crossing other connections.
</p>

<p>
Moving components and learning the routing
tool made the process easier.
</p>

</details>

<details>
<summary><strong>Problem 5 - DRC Warnings</strong></summary>

<p>
My first DRC check reported 19 warnings.
</p>

<p>
Most were caused by silkscreen graphics
overlapping solder-mask openings.
</p>

<p>
I modified the footprint graphics
and reduced the warnings to one.
</p>

</details>

<hr>

<h2>What I Learned</h2>

<p>
Before starting Starbie, I thought PCB
design mainly involved connecting
components together.
</p>

<p>
Now I understand that there are
several different stages.
</p>

<ol>
  <li>Create the schematic.</li>
  <li>Choose the correct components.</li>
  <li>Assign matching footprints.</li>
  <li>Arrange the physical layout.</li>
  <li>Route the copper tracks.</li>
  <li>Add copper zones where needed.</li>
  <li>Run design checks.</li>
  <li>Export manufacturing files.</li>
  <li>Verify the parts and manufacturing requirements.</li>
</ol>

<p>
I also learned that troubleshooting
is a big part of electronics.
</p>

<p>
A lot of my time wasn't spent drawing
the circuit. It was spent understanding
problems and figuring out how to fix them.
</p>

<p>
This project made me more confident
about learning new technical tools.
</p>

<hr>

<h2>What I Would Improve</h2>

<h3>Component Compatibility</h3>

<p>
I want to verify the exact dimensions
and pinouts of the OLED, MPU6050,
buttons and XIAO ESP32-C3.
</p>

<h3>Silkscreen Labels</h3>

<p>
I would like to improve the printed
labels so the connectors are easier
to identify when assembling the board.
</p>

<h3>Component Placement</h3>

<p>
I want to check the physical clearance
around the sensors and display.
</p>

<h3>Documentation</h3>

<p>
I want to add more screenshots showing
the schematic, PCB layout and design checks.
</p>

<h3>Testing</h3>

<p>
Once the physical PCB is manufactured,
I want to test the connections and
make sure the components work correctly.
</p>

<hr>

<h2>Future Plans</h2>

<p>
The next goal is to turn Starbie
into a working physical device.
</p>

<p>
I want to:
</p>

<ul>
  <li>Verify all component footprints.</li>
  <li>Get the PCB manufactured.</li>
  <li>Assemble the components.</li>
  <li>Program the ESP32-C3.</li>
  <li>Display expressions on the OLED.</li>
  <li>Add button interactions.</li>
  <li>Detect shaking and tilting.</li>
  <li>Display temperature and humidity.</li>
  <li>Experiment with simple animations.</li>
  <li>Design an enclosure for the PCB.</li>
</ul>

<hr>

<h2>Project Status</h2>

<table>
  <tr>
    <th>Task</th>
    <th>Status</th>
  </tr>
  <tr>
    <td>Create KiCad Project</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Import Libraries</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Create Schematic</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Assign Footprints</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Arrange PCB Components</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Route Copper Tracks</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Add Ground Plane</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Run DRC</td>
    <td>Completed - 1 warning remains</td>
  </tr>
  <tr>
    <td>Export Gerber Files</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Inspect Gerber Files</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Create BOM</td>
    <td>Initial version completed</td>
  </tr>
  <tr>
    <td>Verify Physical Components</td>
    <td>Still to do</td>
  </tr>
  <tr>
    <td>Assemble PCB</td>
    <td>Not started</td>
  </tr>
  <tr>
    <td>Program Starbie</td>
    <td>Not started</td>
  </tr>
</table>

<hr>

<h2>Project Files</h2>

<ul>
  <li><code>Starbie-PCB.kicad_pro</code> - KiCad project</li>
  <li><code>Starbie-PCB.kicad_sch</code> - Schematic</li>
  <li><code>Starbie-PCB.kicad_pcb</code> - PCB layout</li>
  <li><code>Gerbers/</code> - Manufacturing files</li>
  <li><code>BOM.md</code> - Bill of materials</li>
  <li><code>JOURNAL.md</code> - Development journal</li>
</ul>

<hr>

<h2>Project Screenshots</h2>

<p>
This section will contain screenshots
of my design process.
</p>

<h3>Schematic</h3>
<p>Add schematic screenshot here.</p>

<h3>PCB Layout</h3>
<p>Add PCB layout screenshot here.</p>

<h3>Ground Plane</h3>
<p>Add ground plane screenshot here.</p>

<h3>DRC Results</h3>
<p>Add DRC screenshot here.</p>

<h3>Gerber Viewer</h3>
<p>Add Gerber Viewer screenshot here.</p>

<hr>

<h2>Development Timelapse</h2>

<p>
I recorded part of my development process
using Hack Club Lapse.
</p>

<p>
<a href="https://lapse.hackclub.com/timelapse/-okA6pEqrZLI">
Watch my Starbie development timelapse
</a>
</p>

<hr>

<h2>Final Thoughts</h2>

<p>
This project took much longer than I
expected when I first started.
</p>

<p>
I spent around five and a half hours
working through KiCad and trying
to understand everything.
</p>

<p>
I was so focused on finishing the
PCB that I continued working
through dinner without getting up.
</p>

<p>
There were moments when I honestly
had no idea what I was supposed
to do next.
</p>

<p>
The most difficult parts were
importing the libraries,
understanding footprints,
routing the PCB and fixing
the design warnings.
</p>

<p>
But each problem helped me
learn something new.
</p>

<p>
The best part was finally
seeing the PCB fully routed
with zero unconnected items.
</p>

<p>
Even though the physical
device hasn't been built yet,
I'm happy that I managed
to complete my first PCB design.
</p>

<p>
If I were starting again,
I would spend more time
checking component footprints
before routing the board.
</p>

<p>
I'm looking forward to
the next stage and hopefully
turning Starbie into a
working digital pet.
</p>

<hr>

<div align="center">

<p>
<strong>Made for Hack Club Half Life - Week 1</strong>
</p>

<p>
My first PCB design, and definitely not my last.
</p>

</div>
