---
layout: default
title: Notes on Teleportation
nav_order: 1
parent: Notes
---
# Notes on Teleportation

Teleportation is a simple mechanic to implement, but a difficult mechanic to implement well. Teleportation has a lot of depth.

See the [Glossary entry on Teleportation](../glossary/Locomotion/Teleportation.md) for definitions.

## Orientation & Landmarks
It is considered a good practice not to re-orient the player when they teleport. They should be facing the same world-relative direction at the start and end of the teleportation. If a recognizable landmark is in the distance visible, and they teleport closer to it, it should still be visible. If the player teleports to in front of a work-bench, for example, the system should probably not "helpfully" snap the player to be facing that work bench. The player should initiate this turn themselves, either through controller input when selecting the destination or by just turning their body. 

We may wish to allow the player to re-orient themselves (their rotation) during the teleportation. The teleportation destination marker may include an arrow or indicator of some kind informing the user which direction they are going to be pointed when they teleport. 

## Selection Accuracy 
Selecting a destination with a straight-line laser-pointer style selection is difficult for players. The required accuracy of their pointing increases exponentially as the distance away from themselves increases. To counter this, one common solution is to show the teleportation as a parabolic arc, calculated like a thrown object. This allows a change in the angle of the controller to more consistently map to a change in the distance of destination.

## Range
It is often desired to limit the range of the users teleportation destinations. This is often important from a design perspective, as it forces the user to be more aware of their surroundings and the path they take through an environment. It helps with the above issue of selection accuracy. It can be annoying for a player to teleport multiple times to reach a further destination. One would want to design environments that avoid "long straight hallways" when using this form of teleportation. 

## Mid-Teleportation Animation
The most common effect is not to instantly snap the user to a new location, but to quickly fade the screen to black. This is effective at reducing disorientation. 

Another commonly used animation is to quickly move the player along a path while they are teleporting. This is often used when the player is connected to an avatar that needs to move through the world to check for collisions. This can be uncomfortable, especially if done slowly. It is recommended to instantly speed the player up to the movement speed, and instantly stop moving them when they reach the destination, as velocity tends to be less troublesome than acceleration in terms of motion sickness. While doing this, introducing a screen vignette to darken or black-out the periphery also helps prevent motion sickness.

<div style='position:relative; padding-bottom:calc(56.25% + 44px)'><iframe src='https://gfycat.com/ifr/AlarmedThirdIberianlynx' frameborder='0' scrolling='no' width='100%' height='100%' style='position:absolute;top:0;left:0;' allowfullscreen></iframe></div>
*The lab showing the player being linearly interpolated between the destinations. Also showing a form of zone-based teleportation.*

Particle effects, or a pre/post "dust trail" can help inform the user of the motion they just made, as well as inform other users in a multiplayer experience of what even happened. ex: **The Museum of Other Realities**.

## Granular Teleportation Notes
Granular Teleportation can be easier to implement than zone-based teleportation from a design perspective, but it is more challenging and asks for more attention from the user as a skill, which can lessen the sense of presence.

It is difficult for the user to know where they are in the real world, while still requiring them to be obliquely aware of such information in order to teleport effectively.

Granular teleportation discourages physical movement. Users often tend to just keep teleporting, which is immersion-breaking and makes building presence difficult. Yet sometimes this is crucial for accessibility, and to work with users with limited or impaired mobility.

With granular teleportation, some users find a way to get themselves stuck with a disconnection between virtual and real spaces. For example, I have gotten myself into a situation where the real-world wall was right in front of me, and a virtual wall was right behind me. I found it difficult to break my virtual presence and walk through the virtual wall in order to try and reset myself.

## Zone-Based Teleportation Notes
Zone-based teleportation is easy for the user to understand and it keeps player away from real-world walls or from over-relying on teleportation, allowing presence to be build more easily. It is generally more difficult to design for and implement, especially in a situation where your level was not designed for VR, like an architecure sim or port of a video game.

## Play Area Overlay
One method for tackling the difficulty of granular teleportation for players is to show the player an outline of their play-area space while teleporting. While this does helps, it asks the player to be aware of their real-world space at all times. ex: Valve's **The Lab**. 

I think it is a good idea to let such an outline be enabled in the settings, or only enable it when it seems that the player may likely need the assistance, such as if they are teleporting multiple times without taking other actions, or the destination they are in the process of selecting would largely overlap the play area with out-of-bounds areas.

### GDC Talk by OWLchemy Labs.
The following GDC Talk includes an excellent analysis of zone-based and granular teleportation, as well as their pros and cons.

<iframe width="560" height="315" src="https://www.youtube.com/embed/q83f3sdQBBc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>