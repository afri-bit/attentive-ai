---
title: System Architecture
---

# System Architecture

!!! note
    **DISCLAIMER**: Don't expect a *professional* system architecture!

The **AlpacAI** system originated from a hackathon event, necessitating the architecture to be designed within a rigorous 2 to 2.5-days development timeframe. Consequently, we aimed for simplicity in our architectural approach while ensuring that it remained innovative and cutting-edge.

For a high-level overview of our system, please refer to the following diagram.

<br/>
<div markdown="span" sytle="justify-content: center; display: flex;">
    ![](../../../_assets/img/system_architecture.drawio.svg)
</div>

## Basic Idea

Let's break down the architecture into different sections, so you can have the idea why we designed this architecture at the first place.

### Core Purpose

In this section, let's focus on the *yellow* part of the architecture. We call this the **core** purpose of the whole system.

<br/>
<div markdown="span" sytle="justify-content: center; display: flex">
    ![](../../../_assets/img/system_architecture_yellow.drawio.svg)
</div>
<br/>

This specific construction has a strong relation with the *core* value of **AlpacAI** system. So what do we see in this in this picture?  
Since we want to make the driving experience a safe place for the driver itself, we want to detect the driver drowsiness level using the camera detection approach. The result of the detection will be sent to the middleware system for further processing. Based on this result and other information, the decision maker function component will decide the activation of the conversation agent.

The *conversation agent* has the main purpose to interact with the driver during the driving to increase driver attention during driving time. It has different stages to interact with the driver based on the driver attention level during driving

1. Joyful Ride - Entertainment  
   In this stage the entertainment system will be turned on automatically, so the driver has a joyful ride while listening to music, radio or even podcast.

2. Knowledgeful Ride  
   Based on the location of the driver / vehicle, the conversation agent will engage a conversation with the driver by asking different type of questions, and the system will expect an answer from the driver within certain amount of time frame. 

3. Need Your Attention  
   This stage has similar behaviour as the previous stage, but the conversation will expect response from the driver within shorter time frame. 

4. Annoy Until You Obey  
   The system will start to activate the acoustic engagement with the driver, e.g. vibrating steering wheel, beeping sound, etc. 

### Middleware

The middleware is responsible for maintaining the communication between different systems. 


### Vehicle Information

The vehicle information is crucial for the decision maker function component. This determined how the whole system behaves.

<br/>
<div markdown="span" sytle="justify-content: center; display: flex">
    ![](../../../_assets/img/system_architecture_vehicle.drawio.svg)
</div>
<br/>

The main information, that will be retreived from the vehicle, are the location of the vehicle and vehicle speed.

* Vehicle Location  
  With vehicle location, the conversation agent will gather information from surrounding area to start a conversation with the driver. The conversation can be a form of knowledgeful question, such as question about famous / historic building from the surrounding area, or any other interesting topic about specific area.

* Vehicle Speed  
  This information will determine the minimum limit of vehicle speed to activate the conversation agent.