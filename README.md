# HalfLife-Project-Week-1

Starbie - My First PCB Project

About the Project

Starbie is my first PCB design project, which I made for Hack Club Half Life Week 1. The idea is to create a small digital pet that can interact with people using buttons, sensors and a display.

Before starting this project, I had some basic coding knowledge, but I had never properly designed a PCB before. I didn't really know how KiCad worked, what footprints were, or how a schematic was turned into an actual circuit board.

I decided to follow the Starbie starter project because it looked like a good way to learn the basics of electronics and PCB design without needing physical components straight away.

I used KiCad 10 on my Mac to make the schematic, design the PCB, route the tracks and export the manufacturing files.

The project took me quite a while because almost everything was new to me. There were many times when I got confused about what I was supposed to click or why something wasn't working, but I eventually managed to get through most of those problems.

By the end, I had a routed PCB, exported Gerber files, a bill of materials and a GitHub repository containing my project.

The actual physical Starbie hasn't been built yet. For now, this repository contains the PCB design and the work I completed during the design stage.

Why I Chose Starbie

I wanted to make something that wasn't just a basic circuit with an LED turning on and off.

The idea of making a digital pet sounded interesting because it combines several different things. It needs a microcontroller to control everything, a screen to display expressions, buttons for interaction and sensors to detect changes in its surroundings.

I also liked the fact that I could eventually program it to have different reactions and behaviours.

For example, Starbie could show a happy expression when someone presses a button, react when it is tilted or shaken, or display the room temperature.

These are features I want to work on during the programming and building stages. They haven't been implemented in hardware yet.

Another reason I chose this project was that it seemed manageable for someone who was completely new to PCB design.

I knew it would still be challenging, but having a starter guide made it easier to understand what I needed to do.

Components Used in the Design

1. Seeed Studio XIAO ESP32-C3

The XIAO ESP32-C3 is the main controller for Starbie.

It is responsible for communicating with the other components and will eventually run the code that controls Starbie's behaviour.

I chose this board because it is small and provides the pins needed for the project.

One of the first things I had to learn was how to identify the different pins on the schematic.

At first, labels such as D1, D2, D3, GND, VBUS and 3V3_OUT were confusing. I had to understand that not every pin does the same thing and that connecting the wrong pins could cause problems.

2. OLED Display

The OLED display will be used to show Starbie's face and other information.

I included a four-pin I2C OLED connector in the PCB design.

The display uses two communication signals called SDA and SCL.

I learned that SDA is used for data, while SCL provides the clock signal used for communication.

The OLED is planned to display different expressions, animations and possibly simple information such as temperature.

3. MPU6050 Motion Sensor

The MPU6050 is a motion sensor that can measure acceleration and rotation.

I included a connector for an MPU6050 module so Starbie can eventually detect movement.

For example, I want Starbie to react when someone picks it up, tilts it or shakes it.

The motion sensor also uses I2C communication, meaning it can share the SDA and SCL lines with the OLED display.

I hadn't worked with I2C before, so learning how multiple components can use the same communication bus was interesting.

4. DHT11 Temperature and Humidity Sensor

The DHT11 measures temperature and humidity.

I added this sensor because I wanted Starbie to be able to respond to its environment rather than only to button presses.

The sensor has power, ground and data connections.

I also included a 10k ohm pull-up resistor on its data line.

Initially, I didn't really understand why a resistor would be needed there, but I learned that pull-up resistors help keep certain signal lines at a defined high voltage when they are not being actively pulled low.

5. Push Buttons

I added two push buttons to control Starbie.

The buttons are connected to the ESP32-C3 GPIO pins and ground.

My plan is to use them for different interactions, such as changing Starbie's expression, switching modes or selecting options.

When creating the schematic, I learned how a push button can connect an input pin to ground when pressed.

I also learned that the actual footprint of a button matters because the physical switch needs to fit the pads on the board.

6. Custom PCB

The PCB connects all the components together.

Instead of having wires running between everything on a breadboard, the circuit board uses copper tracks to make those connections.

This was the main part of the project for Week 1.

I designed a two-layer PCB, routed the required connections and added a ground copper zone.

Software and Tools

KiCad 10

KiCad was the main software I used.

I used it for creating the schematic, managing component libraries, assigning footprints, laying out the PCB, routing copper tracks, running design checks and exporting manufacturing files.

At first, the interface was quite overwhelming because there were so many menus, layers and tools.

After spending time using it, I started understanding the difference between the Schematic Editor, PCB Editor, Footprint Editor and Gerber Viewer.

GitHub

I used GitHub to store my project files and documentation.

The repository contains my KiCad design folder along with the BOM, journal and README.

I wanted to keep everything organised so that someone else could understand what I was trying to make and see my progress.

Lapse

I used Hack Club Lapse to record my work while designing the PCB.

This allowed me to document the process rather than only showing the finished result.

It also helped me keep track of the time spent actively working on the project.

How I Designed the Schematic

The first major task was creating the schematic.

I started by installing KiCad and creating a new project called Starbie-PCB.

I then opened the Schematic Editor, which initially showed a blank page.

Before adding components, I needed to import the custom library for the Seeed Studio XIAO ESP32-C3.

This was one of the first things that confused me.

The downloaded care package contained several types of files, including symbols, footprints and 3D models. I didn't initially understand what each file was used for.

I eventually learned that schematic symbols and PCB footprints are separate things.

The symbol is used in the circuit diagram, while the footprint describes the physical pads and dimensions of the component on the board.

After setting up the symbol library, I placed the XIAO ESP32-C3 in the schematic.

I started with the power connections.

I added GND symbols and connected the ground pins, then worked on the 3.3V connection.

After that, I added two push buttons and connected them to the appropriate GPIO pins.

I added connectors for the OLED and MPU6050, followed by the DHT11 sensor and its pull-up resistor.

I had to pay attention to the pin labels so that the components were connected to the correct signals.

By the time I finished the schematic, I had a much better understanding of how all the parts of Starbie were supposed to communicate.

My First Major Mistake

One of the biggest mistakes I made was accidentally connecting the 3.3V power line to ground.

At the time, I was still learning how to draw wires in KiCad.

Some of the connection points were quite close together, and I connected the power symbol to the wrong pin.

I didn't immediately realise what I had done.

After looking more carefully at the schematic, I noticed that the connection was wrong and needed to be fixed.

I removed the incorrect wire and reconnected the 3.3V symbol to the correct pin.

This taught me that even a small wiring mistake can make a big difference in electronics.

It also made me more careful about checking the actual pin names instead of just connecting wires based on where they appeared on the screen.

Understanding Footprints

Footprints were probably one of the most confusing parts of the project for me.

When I first opened the footprint assignment window, I saw a huge list of libraries and component names.

I didn't understand why I needed to select another representation of a component when I had already added it to the schematic.

Eventually, I understood that the schematic only describes electrical connections.

The PCB needs physical information, including where the pins are, how large the pads should be and how much space the component occupies.

I assigned footprints for the XIAO ESP32-C3, two push buttons, DHT11 sensor, resistor and the OLED and MPU6050 connectors.

The XIAO footprint came from the custom library provided in the care package.

For the other parts, I searched the available KiCad libraries and selected footprints that appeared to match the components.

I still need to verify the exact physical dimensions and pin arrangements against the components I plan to purchase.

This is something I want to check carefully before manufacturing the board.

Moving From the Schematic to the PCB

Once the schematic and footprint assignments were ready, I opened the PCB Editor.

I used the Update PCB from Schematic feature to transfer the components into the board layout.

At first, everything appeared grouped together, with lots of thin lines connecting different pads.

I learned that these lines are called ratsnest lines.

They show which electrical connections still need to be routed.

The next task was arranging the components in a sensible layout.

I placed the XIAO ESP32-C3 near the centre, the buttons toward one side, the OLED connector near the top and the sensor connections around the remaining space.

I also had to think about the USB connector on the ESP32-C3, since it needs to remain accessible once the board is assembled.

Another thing I learned was that placing components close together can make routing more difficult.

I moved and rotated parts several times before settling on the layout.

The current layout is a design-stage arrangement, and I still want to check the physical clearance around the actual modules.

Routing the PCB

Routing was another completely new experience for me.

I learned that PCB tracks are the copper connections that replace the wires shown in the schematic.

In the PCB Editor, I selected the front copper layer and used the routing tool to connect pads.

At first, I was unsure how to make tracks turn corners or how to connect them without overlapping other connections.

As I continued, I became more comfortable using the routing tool.

I also started understanding why component placement matters so much.

Sometimes a connection that looked simple on the schematic was more difficult to route on the actual PCB.

I had to work around existing tracks and find suitable paths between components.

After routing the connections, KiCad showed zero unrouted items.

That was one of the most satisfying moments of the project because I could finally see the complete circuit board layout.

Adding the Ground Plane

After routing the PCB, I added a ground copper zone on the back copper layer.

Before this project, I didn't know what a ground plane was.

I learned that instead of drawing individual ground tracks everywhere, a copper-filled area can provide a common ground connection across part of the board.

In KiCad, I selected the B.Cu layer and created a copper zone assigned to GND.

I then drew the zone boundary and filled it.

This was confusing at first because there were several settings related to clearances, fill styles and pad connections.

I used a solid fill with thermal relief connections.

Once the zone was filled, I could see the copper area covering the back of the PCB while maintaining clearances around other electrical connections.

This helped me understand how two-layer PCBs can use copper on both sides.

Design Rule Checking

One of the most useful tools I discovered was KiCad's Design Rules Checker, also called DRC.

After completing the layout, I ran DRC to check for problems.

The checker initially reported 19 warnings.

At first, I thought I had made a lot of electrical mistakes.

After reading the warnings, I realised that most of them were related to the silkscreen graphics on the XIAO ESP32-C3 footprint.

The silkscreen is the printed text and outlines that appear on the PCB.

Some of the footprint's silkscreen graphics overlapped the openings around the solder pads.

I investigated these warnings and modified the footprint graphics.

After making the changes, the warning count dropped from 19 to one.

The remaining warning reported that the XIAO footprint on the PCB differed from the saved library version.

This appears to be related to the footprint modifications I made.

My latest DRC results were:

Errors: 0

Warnings: 1

Unconnected items: 0

Schematic parity issues: 0

I was happy with this progress because it showed that KiCad wasn't reporting any remaining unrouted connections or schematic parity problems.

However, I understand that passing DRC doesn't automatically mean the PCB is guaranteed to work.

I still need to confirm that the actual parts match the footprints and that the remaining library mismatch is limited to the intended changes.

Exporting the Gerber Files

After completing the main PCB layout, I moved on to exporting the manufacturing files.

I learned that PCB manufacturers don't usually manufacture boards directly from the KiCad editing window.

Instead, they use files called Gerbers, along with drill files.

Gerber files describe different manufacturing layers of the PCB.

These include the copper layers, solder masks, silkscreen and board outline.

The drill files specify the holes that need to be made in the board.

I exported the relevant layers and generated the plated and non-plated drill files.

After exporting them, I opened KiCad's Gerber Viewer.

At first, the preview was confusing because several coloured layers appeared on top of one another.

I learned how to turn individual layers on and off so I could inspect them separately.

I checked that the copper tracks, pads, drill holes and rectangular board profile appeared in the exported files.

This was another important part of the project because it showed me what information a PCB manufacturer actually receives.

Bill of Materials

I also created a bill of materials, usually called a BOM.

The BOM lists the parts required to assemble Starbie.

My list includes the XIAO ESP32-C3, OLED display, MPU6050 module, DHT11 sensor, two push buttons, pull-up resistor, connectors and custom PCB.

I searched for suppliers and compared part prices.

My initial list was more expensive than I wanted, so I looked for lower-cost alternatives.

One example was the XIAO ESP32-C3, where I found a cheaper listing from Seeed Studio.

This helped reduce the parts subtotal.

The BOM currently needs a final shipping and compatibility check before purchasing.

I also learned that the cheapest part isn't always the cheapest option overall, because shipping costs and minimum order quantities can make a big difference.

For a future revision, I would like to simplify the purchasing process by reducing the number of different suppliers where possible.

Things That Confused Me

There were quite a few moments when I got stuck during this project.

Importing libraries

I initially had problems understanding how KiCad stores custom symbol and footprint libraries.

I had to learn about project-specific library tables and how to point KiCad toward the correct files.

Assigning footprints

I spent time figuring out which footprints belonged to which components.

The list of available footprints was much larger than I expected, and it wasn't always obvious which one to choose.

Drawing wires

At first, I sometimes connected wires to the wrong pins or wasn't sure whether a wire had properly attached to a connection point.

This made me realise how important it is to zoom in and check the pin labels.

PCB layers

It took me time to understand the difference between F.Cu, B.Cu, F.Silkscreen, B.Silkscreen and Edge.Cuts.

I eventually learned that each layer has a different purpose.

Design warnings

The 19 DRC warnings were confusing because I didn't initially know which objects KiCad was referring to.

I had to learn how to inspect individual warnings and understand the difference between silkscreen graphics and actual electrical connections.

Gerber Viewer

When I opened the Gerbers for the first time, the overlapping layers made it difficult to see the board clearly.

Turning individual layers on and off made the preview much easier to understand.

What I Learned

This project taught me much more than I expected.

Before starting, I mainly thought PCB design meant drawing electronic connections.

Now I understand that there are several different stages involved.

First, the schematic describes how components are connected electrically.

Then each component needs a footprint that represents its physical connections.

After that, the components need to be arranged on the circuit board.

The copper tracks must be routed, ground connections need to be considered and the board outline must be defined.

Finally, design checks and manufacturing exports help identify issues before a physical PCB is ordered.

I also learned the importance of troubleshooting.

A lot of the time I spent on this project wasn't just placing components or drawing tracks.

It was figuring out why something wasn't working, researching unfamiliar concepts and correcting mistakes.

The project made me more comfortable using technical software that I had never used before.

What I Would Improve

Even though I've completed the main design, there are several improvements I would like to make.

Verify component compatibility

I want to check the exact pinouts and dimensions of the OLED, MPU6050 module, push buttons and XIAO ESP32-C3.

This is important because two components can have similar descriptions while using different physical layouts.

Improve the silkscreen

I want to make the board's printed labels clearer and easier to read.

I would also like to add useful labels for the connectors so that assembling the PCB becomes easier.

Review component spacing

I want to make sure there is enough room for the actual sensor modules, not just the small connector footprints.

Improve the documentation

I plan to include clear screenshots of the schematic, PCB layout and Gerber files so that someone else can follow my work.

Test the physical board

Once the design has been reviewed and the correct components are available, the next step would be assembling the PCB and testing it.

Future Plans

The next major goal is to turn the PCB design into a working physical Starbie.

First, I need to finish verifying the components and prepare the design for manufacturing.

After that, I want to order the PCB and parts, assemble everything and start programming.

Some features I would like to add include:

Different facial expressions on the OLED screen

Button-controlled interactions

Reactions to shaking or tilting

Temperature and humidity information

Simple animations

Different moods or states

A basic menu system

A small enclosure to protect the PCB

I also want to learn more about programming the ESP32-C3 and communicating with multiple sensors.

Eventually, it would be interesting to make Starbie feel more like a small companion rather than just an electronics project.

Project Status

Task

Status

Create KiCad project

Completed

Import custom libraries

Completed

Draw schematic

Completed

Assign footprints

Completed

Arrange PCB components

Completed

Route copper tracks

Completed

Add ground copper zone

Completed

Run DRC

Completed, one warning remains

Export Gerber files

Completed

Export drill files

Completed

Inspect Gerber files

Completed

Prepare BOM

Completed initial version

Verify actual component compatibility

Still to do

Assemble physical PCB

Not started

Program Starbie

Not started

Test physical device

Not started

Project Files

The repository contains the project files used during the design process.

The main files are:

Starbie-PCB.kicad_pro — KiCad project configuration

Starbie-PCB.kicad_sch — Circuit schematic

Starbie-PCB.kicad_pcb — PCB layout

Gerbers/ — Exported manufacturing files

BOM.md — Bill of materials

JOURNAL.md — Development progress

The custom symbol and footprint libraries are also required to open and edit the complete design.

Design Screenshots

I plan to include screenshots of the following:

My full KiCad schematic

The PCB layout with all components

The routed copper tracks

The filled ground plane

The DRC results

The board in Gerber Viewer

These screenshots will make it easier to understand how the design progressed from an initial schematic to a routed PCB.

Development Timelapse

I recorded part of the development process using Hack Club Lapse.

The recording shows my work on the Starbie project.

Watch my Starbie development timelapse

Final Thoughts

This project was definitely more challenging than I expected when I first started.

I spent around five and a half hours working through KiCad, and by the end I felt like I had been staring at the same circuit board forever.

At one point, I was so focused on getting everything working that I continued through dinner without getting up.

There were several times when I had no idea what I was supposed to do next, especially while importing libraries, assigning footprints and fixing the DRC warnings.

But each problem taught me something new.

The best part was finally seeing the complete PCB layout with all the tracks routed and zero unconnected items.

Even though I haven't built the physical device yet, I'm happy that I managed to create my first PCB design and understand much more about how electronics projects are put together.

If I were starting this project again, I would probably spend more time checking component footprints before beginning the PCB layout. That would make the later stages easier.

For now, I'm looking forward to the next stage of Starbie and hopefully seeing the design become a real working device.

This project was made for Hack Club Half Life Week 1.
