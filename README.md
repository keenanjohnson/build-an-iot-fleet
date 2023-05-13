# How to Build an IoT (Internet of Things) Fleet
This is a getting started guide for building your own IoT fleet.

If you are starting to build your own fleet of connected devices, consider this a field guide of sorts. It may also be helpful existing fleets that are exploring expansions or alternatives.

If this is helpful to you, consider giving it a star!

## Hardware
You have a lot of choices to make in hardware. Each of these choices has strengths, weaknesses, and will affect the software system needed to power your fleet.

### Compute Unit

One of the most important things to cnsider first, is what your hardware selection will be. 

The most impactful choice is whether the compute unit for the project will be a microcontroller (MCU) or more powerful system (example: Raspberry Pi) that can run a full operating system (example: Linux).

### Communication Technology
Some options to consider:
* Wifi - The cheapest, at the expense of lower range and hgher power requirements. The main benefit is that no recurring costs are incurred by the fleet owner as wifi is usually paid for by customers. However, a robust onboarding process will need to be developed to allow users to connect and change the devices wifi. 
* Cellular/GSM/LTE
* LoRaWAN
* Amazon Sidewalk - A new network using Bluetooth Low Energy (BLE) and 900 megahertz to create an 

## Software
Writing software is the secret sauce that powers any excellent fleet. The choices in tools and quality of the software will dominate the user experience of the fleet.

I discuss several functions / features each IoT fleet will need below. I've included some reccomended software tools for helping with each that I personally use and enjoy. This list is intended to be a curated list, and therefore not complete. 

If you are familiar with the space, you may notice some offerings from very large companies are missing (AWS IoT for example). It's not that these tools from big corps. aren't functional and useful, but rather I have a hard time reccomending them to anyone looking for advice. My general rule is that a company can focus on only a few key usecases well and IoT is a small market share for most large tech companies. Therefore, it's too easy for a company to [shutter a whole division and leave you, the end user, holding the bag.](https://techcrunch.com/2022/08/17/google-cloud-will-shutter-its-iot-core-service-next-year/). So I generally look for companies that focus only on serving IoT or have a robust open-source policy that will allow you to continue using the tool even if the parent company decideds to cease supporting it.

### Over-the-Air Updates (OTA Updates)
Argubably the most important feature of any fleet is that ability to update software on devices in the field or with customers. This helps you continously provide value to customers, fix problems easily, and ensure devices are secure. 

#### Reccomended Tools for Embedded Linux:
* [Balena](https://www.balena.io/) / [Balena Github](https://github.com/balena-io) - Balena is my go to tool for any high level compute IoT project. It is built on top of Yocto linux and allows you to easily deploy one or more docker containers to edge devices. This solves the major headache of embedded linux, ensuring dependancies and the OS are as tightly controlled as the application code.

#### Reccomended Tools for MCUs / Microcontrollers:
* [Golioth](https://www.golioth.io/) / [Golioth Github](https://github.com/golioth) - Golioth is my go to choice for any microcontroller based project. They have excellent support for devices that run Zephyr RTOS, Espressif devices using esp-idf, infineon devices with Modustoolbox, and a lot more. It's easy and straightforward to push an update to a device and have it reliabily occur.

### Sending Data From Your Device to the Internet (Telemetry)

Reccomended Tools for MCUs / Microcontrollers:
* [Golioth](https://www.golioth.io/) / [Golioth Github](https://github.com/golioth) - In addition to the OTA service, Golioth offers a service to move data off of the device via Light DB and [LightDB stream](https://docs.golioth.io/cloud/services/lightdb-stream). Once on the golioth platform, data can be routed elsewhere to other software tools or databases, like [InfluxDB for example.](https://www.influxdata.com/)

## Author

[Keenan Johnson](https://www.keenanjohnson.com/) is an electrical and software engineer with experience building IoT fleets of all shapes and sizes.

[Reach out](https://www.keenanjohnson.com/consulting) if you need help or are interested in hiring me as a consultant for your project.
