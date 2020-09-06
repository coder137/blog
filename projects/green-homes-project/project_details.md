---
layout: single
title: "Project Details"

# Added table of contents defn
toc: true
toc_label: "Table of Contents"
toc_icon: "cog"

# Modify header
# excerpt: "Knowledge Hub"
# header:
#   overlay_image: "assets/images/tutorials.jpg"
#   overlay_filter: 0
#   caption: "Photo by [*Masaaki Komori*](https://unsplash.com/@gaspanik) on [Unsplash](https://unsplash.com/)"

# Sidebar
# sidebar:
#   nav: "freertos_nav"
author_profile: true
---

Details have been synced with the [Ketto campaign page](https://ketto.org/green-homes-project)


# Green Homes Prototype

This is a demo video that walks you through the process of setting up your components and watering your plants through the mobile application.

<!-- Youtube Embedded link -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/X6MWZNG_73M" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<!-- TODO, Format the youtube link here -->

# Software Architecture

![Plant Watering Software Block Diagram]({{ site.baseurl }}{% link projects/green-homes-project/project_details_images/Software_Block_Diagram.png %})

## Device Configuration

Initially the hardware device does not know your home WiFi settings. Through a nifty program called [APManager](https://github.com/coder137/APManager) a local hotspot is created. 

This Access Point Manager (APManager) provides a REST API for scanning surrounding WiFi signals and can also take in the SSID and Password of the WiFi that the user would like to connect to and stores it in device flash.

The primary user then connects to the device hotspot and supplies the Wifi details to the it. The device needs a stable internet connection to work reliably.

## Default Firmware Loop

The hardware device connects to a pre-configured real-time server and waits for a user action to be performed. In response to a user action sent from the application a specific event is received which triggers different actions on the device.

### Actions supported

- `ACTION_START_WATERING`
  - Used to start watering the plant.
- `ACTION_SET_WATERING_TIME`
  - Used to set the default time the pump is kept switched on.
  - This directly affected how much water the plants would receive.
- `ACTION_SET_ALARM`
  - An automated alarm system that triggers the `ACTION_START_WATERING` event according to its stored time (SNTP synced with the DS3231 chip).

## Mobile Application

The User connects to the real-time server 

- To send commands to the device through the server
- To receive updates from the device through the server

## Collaborators

More than one person can have simultaneous access to the plant watering device.

To register various collaborators a unique collaborator id is provided to the primary user who then adds this unique id to your device.

The collaborator is then added to the access list and can perform the same commands as the primary user

Once a collaborator has been registered he/she can perform the same action as the primary user.

You can be a collaborator to as many devices as you'd like. Even as a primary user you can be added as a collaborator to another users device.

# Final Update

I would like to thank everyone who pledged to the green homes project and helped me develop the various parts of the system. 

Of the funds that I collected I invested most of my time and effort into building 2 core components.

- The PCB Design
- Custom Tubes, Joints and pipes for easy fittings

In the files and images that have been shared you can see the various iterations that my designs have gone through.

## Learning

Since I am a hardware and application developer, making this project has given me significant insight on how to build various interconnected systems and knowledge on various topics.

- Working on server side (Parse Server, Databases and Real-time protocols)
- Working on circuit design and its various intricacies
- A little knowledge about 3D printing and how to start a business.

## Next Steps 

While I do have a working prototype it is still far for being called a complete product.

In the future these are the various areas in which I will invest my time and effort to make the system better

- Improved Real time system design to get instantaneous updates
- Improved Android App usage.
- Improved server optimizations. The current server had 1-2 seconds of lag between requests.
- Custom made parts for customizability. The ready made parts did not fit the project very well.
- 3D Printed Cases to store the PCB designs.
- Update PCB Design to remove all wires while retaining the modularity (Swappable Parts).

In the future if the demand arises I will make all the code and project resources open source so that there can be greater community involvement in designing, collaboration and building toward a common goal.

## Drawbacks

These are the various issues I faced when making the project

- Custom made parts and 3D Printed cases require volume otherwise each individual case would make the processing cost rise astronomically
- Most of the components used in the design contain plastic or rubber in some form, which is not eco-friendly. I would like to re-make everything with silicon or sustainable products if possible.

## Prototype 1

![Main Prototype V1]({{ site.baseurl }}{% link projects/green-homes-project/project_details_images/Prototype_1.png %})

![Power System V1]({{ site.baseurl }}{% link projects/green-homes-project/project_details_images/Power_System_V1.png %})

## Prototype 2


![Main Prototype V2]({{ site.baseurl }}{% link projects/green-homes-project/project_details_images/Prototype_2.png %})

![Power System V2]({{ site.baseurl }}{% link projects/green-homes-project/project_details_images/Power_System_V2.png %})


## Early Modular Design

![Early Modular Design]({{ site.baseurl }}{% link projects/green-homes-project/project_details_images/Early_Prototype.png %})

