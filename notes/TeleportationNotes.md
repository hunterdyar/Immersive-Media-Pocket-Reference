---
layout: default
title: Notes on Teleportation
nav_order: 1
parent: Notes
---
# Notes on Teleportation

Teleportation is a simple mechanic to implement, but a difficult mechanic to implement well. Teleportation has a lot of depth.

See the [Glossary entry on Teleportation](../Glossary/Locomotion/Teleportation.md) for definitions.

## Mid-Teleportation Animation
The most common effect is not to instantly snap the user to a new location, but to quickly fade the screen to black. This is effective at reducing disorientation. 

Another commonly used animation is to quickly move the player along a path while they are teleporting. This is often used when the player is connected to an avatar that needs to move through the world to check for collisions. This can be extremely disorienting. It is recommended to instantly speed the player up to the movement speed, and instantly stop moving them when they reach the destination, as velocity tends to be less troublesome than acceleration in terms of motion sickness. While doing this, introducing a screen vignette to darken or black-out the periphery also helps prevent motion sickness.

Particle effects, or a pre/post "dust trail" can help inform the user of the motion they just made, as well as inform other users in a multiplayer experience of what even happened. ex: **The Museum of Other Realities**.

## Granular Teleportation Notes
Granular Teleportation can be easier to implement than zone-based teleportation from a design perspective, but it is more challenging and asks for more attention from the user as a skill, which can lessen the sense of presence.

It is difficult for the user to know where they are in the real world, while still requiring them to be obliquely aware of such information in order to teleport effectively.

Granular teleportation discourages physical movement. Users often tend to just keep teleporting, which is immersion-breaking and makes building presence difficult. Yet sometimes this is crucial for accessibility, and to work with users with limited or impaired mobility.

With granular teleportation, some users find a way to get themselves stuck with a disconnection between virtual and real spaces. For example, I have gotten myself into a situation where the real-world wall was right in front of me, and a virtual wall was right behind me. I found it difficult to break my virtual presence and walk through the virtual wall in order to try and reset myself.

One method for tackling such troubling and immersion-breaking moments is to show the player an outline of their play-area space while teleporting. While this does helps, it asks the player to be aware of their real-world space at all times. I think it is a good idea to let such an outline be enabled in the settings, or only enable it when it seems that the player may likely need the assistance, such as if they are teleporting multiple times without taking other actions.

## Zone-Based Teleportation Notes
Zone-based teleportation is easy for the user to understand and it keeps player away from real-world walls or from over-relying on teleportation, allowing presence to be build more easily. It is generally more difficult to design for and implement, especially in a situation where your level was not designed for VR, like an architecure sim or port of a video game.

### GDC Talk by OWLchemy Labs.
The following GDC Talk includes an excellent analysis of zone-based and granular teleportation, as well as their pros and cons.

<iframe width="560" height="315" src="https://www.youtube.com/embed/q83f3sdQBBc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>