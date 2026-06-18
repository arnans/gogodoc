# Vernier Go Direct Sensors

<!-- TODO: hero image — GoGo Board showing a live reading from a Go Direct sensor -->
<img src="https://github.com/thegogoboard/gogodoc/blob/main/Vernier/Vernier-sc.png?raw=true" alt="GoGo Board reading a Vernier Go Direct sensor" width="30%"/> <img src="https://github.com/thegogoboard/gogodoc/blob/main/Vernier/Vernier-sc1.png?raw=true" alt="GoGo Board reading a Vernier Go Direct sensor" width="30%"/> 

Now you can connect the GoGo Board to Vernier Go Direct Bluetooth sensors and use them in your STEM projects.

> Requires GoGo Board firmware **v4.0.0** or newer. The Vernier co-processor firmware is released together with the GoGo Board firmware and shares the same version number.

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

Go Direct sensors are a class of Bluetooth sensor modules from Vernier Science Education. There are over 50 sensor modules available. The GoGo Board talks to these sensors over Bluetooth — no wires needed. Putting Vernier's sensors together with the GoGo Board's motors, lights, and other outputs opens up lots of new project ideas.

**A few things you can measure:**

- Temperature, relative humidity, and soil moisture
- Light intensity, UV, and color
- Force, motion, and acceleration & rotation
- pH, conductivity, and CO₂ gas
- Sound level and heart rate (EKG)
- Voltage, current, and wind speed

...and many more. Each Go Direct sensor measures one or more of these.

Here's how it works:

- **From the GoGo Board** — Connect a sensor and watch its live reading right on the GoGo Board's screen.
- **From your code** — Use the `vernier's` block to read a measurement and use it in your program.

  ![](https://github.com/thegogoboard/gogodoc/blob/main/Vernier/GoGo%20x%20Vernier%20(6).gif?raw=true)
   <!-- TODO: image — live sensor reading on the GoGo's screen -->

---

## Getting Started

### Prerequisites

- A GoGo Board with firmware **v4.0.0** or newer.
- The matching **Vernier (C3) co-processor firmware** — it ships with the same release and shares the GoGo Board firmware's version number, so install the version that matches your board firmware. See the [Firmware Update Guide](../firmware-update/firmware-update-guide.md) if you need to update.
- The GoGo Board's **Co-MCU** setting turned on for Vernier (see step 1 below).
- A Vernier Go Direct sensor that is **charged and turned on**.
- For the **first** connection, keep the sensor **right next to** the GoGo Board.

### Connecting a Go Direct Sensor

1. On the GoGo Board, open **Settings** and set **Co-MCU** to **Vernier**. This turns on the Vernier feature and makes the **Vernier Sensor** screen appear.

2. Go to the **Vernier Sensor** screen and pick a slot to use. The GoGo Board has **3 slots**, so you can connect and use up to 3 sensors at the same time.

3. Turn on your Go Direct sensor and keep it close to the GoGo Board. Put the sensor into pairing mode — usually by pressing and holding the button on the sensor.

4. The sensor connects to the slot you picked.

   <!-- TODO: image — connected sensor card / slot on the Vernier screen -->
   <img src="images/vernier-card.png" alt="Vernier card on the left panel" width="30%"/>

5. Once it's connected, you'll see the live reading right on the screen.

> **Tip:** After a sensor is paired once, the GoGo Board remembers it. The next time you turn everything on, it tries to reconnect to that sensor by itself.

### If your sensor won't connect

If a sensor doesn't show up, check these:

- The sensor is **charged and turned on**.
- The sensor is in **pairing mode** (press and hold its button until its light blinks).
- The sensor is **close to** the GoGo Board, especially for the first connection.
- In **Settings**, **Co-MCU** is set to **Vernier**.

Then pick the slot again and try once more.

---

## Using Vernier Sensors in Code

Open the **Vernier** category in the blocks toolbox. There are two kinds of blocks:

- **`vernier's [measurement]`** — gives you the sensor's reading as a number.
- **`vernier's [measurement] unit`** — gives you the unit of that reading (for example `°C` or `N`) as text.

   <!-- TODO: image — the vernier's value and unit blocks -->
   <img src="https://github.com/thegogoboard/gogodoc/blob/main/Vernier/vernier's%20block.png?raw=true" alt="vernier's block" width="50%"/>

Each block comes in two styles:

- A **drop-down** version — pick the measurement you want (Temperature, Force, pH, and many more) from the list.
- A **type-it-yourself** version — type the measurement name if it isn't in the list.

The drop-down is the easiest way to start. Just choose a measurement, and the block reads it from whichever connected sensor provides it.

   <!-- TODO: image — capture the measurement drop-down open -->
   ![](https://github.com/thegogoboard/gogodoc/blob/main/Vernier/GoGo%20x%20Vernier%20(2).gif?raw=true)

> **Tip:** If you use the type-it-yourself block, the name has to match the sensor's measurement (for example `temperature`). The drop-down has the names already, so you don't have to worry about spelling — start there.

### Reading from a specific sensor

If you have two sensors that measure the **same** thing (for example two temperature probes), the plain `vernier's` block reads the one in the lowest slot. To choose exactly which sensor you mean, use the **on slot** blocks:

- **`vernier's [measurement] on slot [1/2/3]`** — the reading from the sensor in that slot.
- **`vernier's [measurement] unit on slot [1/2/3]`** — its unit.

The slot number is the same number shown next to the sensor on the GoGo Board's **Vernier Sensor** screen.

   <!-- TODO: image — the "on slot" block with the slot drop-down -->

---

## Examples

> Connect and pick the sampling rate on the GoGo Board's **Vernier Sensor** screen first. In your program you only **read** the measurement — the block always gives you the latest value.

### Example 1: Show the temperature

Read `vernier's Temperature (°C)` and display it, so you always see the current temperature while your program runs.

   <!-- TODO: image/example — temperature-reading program -->
  <img src="https://github.com/thegogoboard/gogodoc/blob/main/Vernier/Example%20program%20reading%20temperature.png?raw=true" alt="Example program reading temperature" width="50%"/>
  
[Download the working code here](https://code.gogoboard.org/#/program/eeef5ba8-58a3-44e1-86e3-05ce1cc9a266)

### Example 2: Turn on an output when it gets warm

Inside a loop, check if `vernier's Temperature (°C)` is above a number you choose (for example 30). If it is, turn on an LED or a motor. This is a simple way to build an automatic fan or a warning light.
![](https://github.com/thegogoboard/gogodoc/blob/main/Vernier/GoGo%20x%20Vernier%20(1).gif?raw=true)

[Download the working code here](https://code.gogoboard.org/#/program/72e055b4-abb2-4e67-b3d6-f91153fa7ef4)

   <!-- TODO: image/example — "turn on output when warm" program -->

---

## Tips, Specs, and Limitations

- **Supported sensors:** Works with Vernier Go Direct Bluetooth sensors — over 50 different modules, measuring temperature, humidity, force, motion, pH, light, CO₂, and more.
- **How many at once:** Up to **3 sensors** can be connected and used at the same time, one per slot.
- **First connection:** Keep the sensor right next to the GoGo Board the first time you pair it. After that, normal Bluetooth range is fine.
- **Reconnecting:** The GoGo Board remembers the last sensor and tries to reconnect to it automatically after a restart.
- **Reading speed:** You can choose how often the sensor is read on the **Vernier Sensor** screen — from very fast (about 10 times a second) to slow (once every couple of minutes). The default is once per second.
- **Reading in code:** Your program can only **read** sensor values. Connecting sensors and choosing the reading speed are done on the GoGo Board's screen, not in code.
