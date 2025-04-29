---
title: "MagSheet"
excerpt: "Designed and coded firmware for a magnetically controlled Flexible Printed Circuit board with controllable magnetic coils during my time at the Actuated Experiences Laboratory (Axlab) at the University of Chicago."
collection: portfolio
---

During my time at the Actuated Experiences Laboratory, I led the research of our Magsheet project. With Magsheet, we aimed to find new approaches to haptic interface design that builds upon the ideas from the paper [MagneLayer: Force Field Fabrication by Layered Magnetic Sheets](https://dl.acm.org/doi/10.1145/3313831.3376552). While MagneLayer demonstrated the power of combining layered magnetic fields for haptic interactions, Magsheet takes the concept further by integrating these magnetic patterns into a flexible PCB.

# Core Features:

- **Ultra-Thin Form Factor:** By embedding magnetic field generators directly onto a flexible PCB, Magsheet can be as thin as a sheet of paper, enabling seamless integration into books, folders, clothing, or ultra-slim devices.
  
- **Flexibility:** Magsheet can wrap around objects like handles, wearables, or irregular surfaces, bringing dynamic haptic feedback to areas where rigid materials would fail.

- **Additional Sensing:** Magsheet allows for electronic control of the magnetic fields. This opens the door to dynamic changes in feedback over time, controlled by software or sensors (for example, using hall-effect sensors to detect the position of a magnet, and then using Magsheet to move it to a specified location).

  
# Example Applications:

- **Interactive Books:** You could place a magnet on top of a page and have it guide the user to where they should be focusing on.

- **Wearable Haptic Systems:** Clothing that can gently guide or alert the wearer through localized magnetic forces.

- **Education and Accessibility Tools:** Tactile learning surfaces for students with visual impairments that can update in real-time.

# Hardware Development:

![Magsheet Control Board](/images/Magsheet_Control_Board.png) 
![Hall Effect Sensor Board](/images/HallEffect_Sensor_Magsheet.png)


# Software Development: 
All firmware was coded by our team using the Arduino IDE. For UI interaction, the Processing library was used. This allowed for quick, on the fly changes while also letting us use several different sensing layers, such as manipulating the magnet with the motor driver while also checking the position of the magnet with the hall-effect sensing board I created, all in one platform. 

# Constraints:

- **Heat:** Magnetic coils can produce a large amount of heat after only a few seconds of operation. These can quickly melt the PET layer of the PCB if not managed properly, so these coils can only ever be used to create magnetic fields in bursts, and not operate them constantly. We could try implementing heatsinks at the cost of weight and flexiblity.
  
- **Power Draw:** When driving these coils, we must use motor units that can draw quite a lot of power compared to the strength of the magnetic field, making lightweight applications using components such as batteries not completely irrelevant, but certainly challenging. 

- **Magnetic Strength:** Ultimately, these coils are being composed of layers of very thin copper traces, and as such their magnetic strength is not large. We have circumvented this by using stronger magnets to compensate. However, in the future, I would like to add a sheet layer of ferromagnetic material to try and enhance the strength of the magnetic field, at the cost of some flexibility. The other benefit, however, would be that some rigidity would be added to the PCB, increasing its material strength. 

- **Trace Fragility:** During a lot of our experiments, we've noted that our flexible PCBs' copper traces could sometimes bend excessively and break. Ultimately, while the form factor is flexible, the copper traces within the PCB is still solid copper, and as such we must be careful with them breaking. We want to implement future designs with reinforced regions that will not be flexible but will protect the traces from being broken as easily. 

# Demo Video:

<video width="100%" controls>
  <source src="/images/Magsheet_Demo_Video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

