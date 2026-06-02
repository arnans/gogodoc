# Vernier Go Direct Sensors

<!-- TODO: hero image — GoGo Board showing a live reading from a Go Direct sensor -->
<img src="images/gogo-w-vernier.png" alt="GoGo Board reading a Vernier Go Direct sensor" width="60%"/>

<!-- TODO: one-sentence pitch. e.g. "Connect Vernier Go Direct sensors to your GoGo Board over Bluetooth and use their measurements in the web app or in your code." -->
Now you can connect the GoGo Board to Vernier Go Direct Bluetooth sensors and use them in your STEM projects.

> Requires **firmware vX.X.X** and a Vernier firmware version x.x.x for the co-processor.

<!-- TODO: confirm minimum firmware version -->

---

## Table of Contents
- [Overview](#overview)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Connecting a Go Direct Sensor](#connecting-a-go-direct-sensor)
- [Using Vernier Sensors in Code](#using-vernier-sensors-in-code)
- [Examples](#examples)
- [Tips, Specs, and Limitations](#tips-specs-and-limitations)

---

## Overview

<!-- TODO: What are Vernier Go Direct sensors? What can you measure (temperature, force,
     motion, pH, etc.)? Why use them with the GoGo Board? -->
Go Direct sensors are a new class of Bluetooth sensor modules from Vernier Science Education. There are over 50 sensor modules available. The GoGo Board communicates with these sensors over Bluetooth. This allows a convenient and robust sensor setup for STEM projects. Combining Vernier's sensors with the GoGo Board's actuator control abilities allows new project possibilities.     

Here's how it works:

- **From the GoGo Board** -- Connect a sensor and view its live reading directly in the GoGo's LCD screen. 
- **From code** -- Use the `Vernier's [sensor]` command to use a measurement as part of your program. 

   <!-- TODO: image — sensor reading shown in the web app -->
   <img src="images/vernier-overview.png" alt="Live sensor reading one the GoGo's LCD screen" width="50%"/>

---

## Getting Started

### Prerequisites

- GoGo Board with firmware **vX.X.X** or newer.  
- GoGo Board co-processor firmware **v.x.x.x** or newer. See the [Firmware Update Guide](../firmware-update/firmware-update-guide.md) if you need to update. 
- The GoGo Board must **be within range** of the Go Direct sensor. On first connect, the sensor must be right next to the GoGo Board. 
- A charged / powered-on Go Direct sensor. <!-- TODO -->

### Connecting a Go Direct Sensor

<!-- TODO: step-by-step pairing flow. Mirror the numbered-steps + inline-image style
     used in image-display.md's "Using the Image Gallery". -->

1. Navigate to the Vernier's control screen on the GoGo Board's LCD. Pick a slot to use. The GoGo Board supports upto 3 slots (3 sensors can be connected and used)

2. Turn on your Go Direct sensor and make sure it is close to the GoGo Board. Put the sensor into pairing mode. This is typically achieved by press-and-hold a button on the sensor. 

3. The sensor should become associated with the selected slot number. 

   <img src="images/vernier-card.png" alt="Vernier card on the left panel" width="30%"/>

4. Once connected, you will see the live reading. 


---

## Using Vernier Sensors in Code

<!-- TODO: which block(s) read a sensor value? what category is it in? -->
Use the `read sensor` command to use a sensor measurement in your program. The command is located in the "..." category. <!-- TODO -->

   <img src="images/vernier-code-block.png" alt="Read sensor command" width="50%"/>

<!-- TODO: explain how to pick the sensor / channel from the drop-down -->

   <img src="images/vernier-code-dropdown.png" alt="Drop-down listing connected sensors and channels" width="30%"/>

---

## Examples

<!-- TODO: 1–2 short worked examples. e.g. display temperature on screen,
     trigger a motor/LED above a threshold, log motion data. -->

### Example 1: <!-- TODO: title -->

   <img src="images/vernier-example-1.png" alt="Example program using a Go Direct sensor" width="50%"/>

---

## Tips, Specs, and Limitations

<!-- TODO: fill in the real constraints. Suggested topics below. -->
- Which Go Direct sensors are supported? <!-- TODO -->
- How many sensors can be connected at once? <!-- TODO -->
- Bluetooth range and reconnect behavior after the board restarts. <!-- TODO -->
- Sampling rate / units / available channels per sensor. <!-- TODO -->
