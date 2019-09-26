---
layout: default
title: Notes on Teleportation
nav_order: 1
parent: Notes
---
# Notes on Teleportation

Teleportation is a simple mechanic to implement, but a difficult mechanic to implement well. Teleportation has a lot of depth.

See the [Glossary entry on Teleportation](../glossary/Locomotion/Teleportation.md) for definitions.

A good teleportation system
- Intuitive
- forgettable
- Clear indications of valid and invalid locations
- Very hard to accidentally select the wrong destination
- Destination marker/parabola marker are not overly noisy/bright/distracting and "fit in" to the design of the world
- The player will know where they end up, and are not disoriented
- Does not obstruct other mechanics
- Limits motion sickness

## Staying out of the way
My personal favorite design implementation of teleportation is from Owlchemy Labs **Vacation Simulator**. It's zone-based teleportation that selects the next direction from gaze direction and a button press. The system gets out of the way and is forgotten as much as possible. If you were to talk about all of the mechanics in Vacation Simulator, you may forget to mention teleportation at all. It's easy to forget about. For such an immersion-breaking mechanic, that's a good thing. One wants the player to be focused on the experience, not on magical glowing parabolas or on selecting a destination that won't have them bonking real-world walls.

It is very important to allow the player to move around without having to think about their real-world environment or relative positioning, and Vacation Simulator pulls this off as well as any teleportation system I have seen so far. 

## Orientation & Landmarks
It is considered a good practice not to re-orient the player when they teleport. They should be facing the same world-relative direction at the start and end of the teleportation. If a recognizable landmark is in the distance visible, and they teleport closer to it, it should still be visible. If the player teleports to in front of a work-bench, for example, the system should probably not "helpfully" snap the player to be facing that work bench. The player should initiate this turn themselves, either through controller input when selecting the destination or by just turning their body. 

We may wish to allow the player to re-orient themselves (their rotation) during the teleportation. The teleportation destination marker may include an arrow or indicator of some kind informing the user which direction they are going to be pointed when they teleport. 

## Laziness and Spamming
<iframe src='https://gfycat.com/ifr/ImportantLimpingGalapagossealion' frameborder='0' scrolling='no' allowfullscreen width='640' height='404'></iframe>
*A player teleporting one foot to pet the dog in *The Lab* instead of moving. 

Laziness through teleporting is a problem. Players are used to in-game locomotion mechancs, and once given one, they often prefer to use the locomotion instead of moving their feet around. Moving around gives the player depth and parallax information that helps create presence, invite discovery/curiosity, and allows for more subtle and intricate design. Moving ones feet through the world creates a sense of presence that is threatened by constant player teleportation. Designing a teleportation system that encourages players to move their feet while not punishing them for teleporting is important.

World design can be a part of the problem. If one is limited in teleportation range yet given long open paths, then the player is likely to spam the teleportation, and get used to doing this for small movements, and not just large area traversal.

<iframe src='https://gfycat.com/ifr/SparseExcellentFieldspaniel' frameborder='0' scrolling='no' allowfullscreen width='640' height='764'></iframe><p> <a href="https://gfycat.com/sparseexcellentfieldspaniel">via Gfycat</a></p>

*A player spamming teleportation in order to cover a large distance in Forestry. Note how the fast mid-teleportation animation, open design, and large paths encourage this behavior, and that the landmarks and limited range means the player almost always can instantly recognize where they are when teleporting.*

## Selection Accuracy 
Selecting a destination with a straight-line laser-pointer style selection is difficult for players. The required accuracy of their pointing increases exponentially as the distance away from themselves increases. To counter this, one common solution is to show the teleportation as a parabolic arc, calculated like a thrown object. This allows a change in the angle of the controller to more consistently map to a change in the distance of destination.

<iframe src='https://gfycat.com/ifr/SpeedyFeminineFieldmouse' frameborder='0' scrolling='no' allowfullscreen width='640' height='764'></iframe><p> <a href="https://gfycat.com/speedyfemininefieldmouse-snow">via Gfycat</a></p>

*Calculating parabolic arc's from the hands position for teleportation improve accuracy and limit range.*

## Range
It is often desired to limit the range of the users teleportation destinations. This is often important from a design perspective, as it forces the user to be more aware of their surroundings and the path they take through an environment. It helps with the above issue of selection accuracy. It can be annoying for a player to teleport multiple times to reach a further destination. One would want to design environments that avoid "long straight hallways" when using this form of teleportation. 

## Obstacle Limitations
You generally want to prevent the teleportation system from allowing the player to teleport into an out-of-bounds area, or into an area that would be uncomfortable, like "into" a table. One must give the player feedback when a destination is invalid. One could make the destination marker only appear when a valid destination is selected - indicating nothing would happen if the player pushed the teleport button. This makes it harder the player to adjust their selection to a valid location, however. I consider it better to give the player feedback. Perhaps show an "invalid" indicator at the destination marker and change the color of a parabola.

If the design of the teleportation system is so noisy that this feedback is distracting to the player, then there are more design problems than just the feedback. 

Another consideration is if the player can teleport "through" objects. It is probably a good idea to prevent them from doing this. If one is teleporting through an object, they probably have a less clear idea of what their destination looks like - no landmark will be visible both before and after the teleportation. This can lead to disorientation.

<iframe src='https://gfycat.com/ifr/DeliciousDifferentBrownbutterfly' frameborder='0' scrolling='no' allowfullscreen width='640' height='764'></iframe><p> <a href="https://gfycat.com/deliciousdifferentbrownbutterfly">via Gfycat</a></p>

Forestry allows players to teleport through objects, but the world is open enough that disorientation or lack of landmarks is not generally an issue.

These limitations can slow a player down naturally, and force them to think before teleporting. Which is probably what we want the player to do, except for cases of large-area traversal.

## Mid-Teleportation Animation
The most common effect is not to instantly snap the user to a new location, but to quickly fade the screen to black. This is effective at reducing disorientation. 

Another commonly used animation is to quickly move the player along a path while they are teleporting. This is often used when the player is connected to an avatar that needs to move through the world to check for collisions. This can be uncomfortable, especially if done slowly. It is recommended to instantly speed the player up to the movement speed, and instantly stop moving them when they reach the destination, as velocity tends to be less troublesome than acceleration in terms of motion sickness. While doing this, introducing a screen vignette to darken or black-out the periphery also helps prevent motion sickness.

<iframe src='https://gfycat.com/ifr/AlarmedThirdIberianlynx' frameborder='0' scrolling='no' controls='0' hd='1' allowfullscreen width='640' height='404'></iframe>

*The Lab showing the player being linearly interpolated between the destinations. Also showing a form of zone-based teleportation.*

Particle effects, or a pre/post "dust trail" can help inform the user of the motion they just made, as well as inform other users in a multiplayer experience of what even happened. ex: **The Museum of Other Realities**.

## Head or Hand Control
Most teleportation systems use controller input for selecting where to look. This is effective for granular teleportation. When using zone-based teleportation, accuracy is not as critical, so long as the zone has a generous selection area. One can, instead of pointing the controller, just select the zone in the direction the player is looking. 

<iframe src='https://gfycat.com/ifr/DifficultSilkyIrishdraughthorse' frameborder='0' scrolling='no' allowfullscreen width='640' height='404'></iframe><p> <a href="https://gfycat.com/difficultsilkyirishdraughthorse">via Gfycat</a></p>

*Zone based teleportation in Vacation Simulator. The destination is controlled by the players head position, not through controller pointing.*

### Gaze Limitation
Given the importance of ensuring the player will know where they will end up when teleporting, should a system limit a player from teleporting somewhere they are not looking? Using head/gaze for destination selection does this inheirently, and is an advantage.

Yet, when using hand control, oen should **not** limit the player to destinations in their field of view. Players will become proficient with the system, and you do not want to artificially lower the skill ceiling by limiting "advanced" moves like teleporting to a destination with the flick of a wrist. Players will feel more annoyed by this limitation than they will be confused if they accidentally press the teleport button.

### Use A Dedicated Button
Ensure that the trigger to teleport (the button) is always very clear. If it is a button on the controller, then ideally the button should only ever teleport the player, and not do anything else. This way the player avoids accidental teleports entirely, and is unlikely to accidentally press it while looking away from the destination marker.

## Lessons From Headbanging
I once created a quick demo where the player teleported not on a button press, but by thrashing their head in the direction they want to go ("headbanging"). It's **not** a good interface, but it's surprisingly not that bad either. The player's own head movement completely covers up the disorientation from the teleportation movement. The hands are completely free to manipulate/hold objects or do control something else. It's surprisingly intuitive (just imagine trying to point someone in a direction with both hands full of groceries), and it's fairly immune to players "spamming" the teleportation button, as teleporting multiple times in a row is inherently uncomfortable.

To be clear, I don't recommend "headbanging" teleportation for a number of accessibility, comfort, and safety reasons. Theres a risk to equipment, which could go flying off, and to faces, which could go flying towards walls. It's also difficult to calibrate when to teleport and when not to, as you want the teleportation to happen with as minimal head movement as possible without false positives. All that being said, the fact that such an absurd control method isn't as bad as it "should be" goes to show that teleportation is far from a "solved" problem in VR, and experimentation is still important.

## Play Area Overlay
One method for tackling the difficulty of granular teleportation for players is to show the player an outline of their play-area space while teleporting. While this does helps, it asks the player to be aware of their real-world space at all times.

I think it is a good idea to let such an outline be enabled in the settings, or only enable it when it seems that the player may likely need the assistance, such as if they are teleporting multiple times without taking other actions, or the destination they are in the process of selecting would largely overlap the play area with out-of-bounds areas.

<iframe src='https://gfycat.com/ifr/WindyPaleCod' frameborder='0' scrolling='no' allowfullscreen width='640' height='404'></iframe><p> <a href="https://gfycat.com/windypalecod">via Gfycat</a></p>

*An overlay of the player's play area boundaries are visible in **The Lab***

## Audio Considerations
OWLchemy labs discuss the importance of audio in the GDC talk linked below.

## Notes on Granular Teleportation
Granular Teleportation can be easier to implement than zone-based teleportation from a design perspective, but it is more challenging and asks for more attention from the user as a skill, which can lessen the sense of presence.

It is difficult for the user to know where they are in the real world, while still requiring them to be obliquely aware of such information in order to teleport effectively.

Granular teleportation discourages physical movement. Users often tend to just keep teleporting, which is immersion-breaking and makes building presence difficult. Yet sometimes this is crucial for accessibility, and to work with users with limited or impaired mobility.

With granular teleportation, some users find a way to get themselves stuck with a disconnection between virtual and real spaces. For example, I have gotten myself into a situation where the real-world wall was right in front of me, and a virtual wall was right behind me. I found it difficult to break my virtual presence and walk through the virtual wall in order to try and reset myself.

# Notes on Zone-Based Teleportation
Zone-based teleportation is easy for the user to understand and it keeps player away from real-world walls or from over-relying on teleportation, allowing presence to be build more easily. It is generally more difficult to design for and implement, especially in a situation where your level was not designed for VR, like an architecure sim or port of a video game.

One advantage of zone-based teleportation is you can teleport the "room", and not the "player position", preventing the player's play-area from ever becoming misaligned from the virtual play-area. This is a huge advantage, and a great reason to design environments for zone-based teleportation. 

Note how in Vacation Simulator, while selecting a teleportation destination, the destination marker will move if the player walks around. 

<iframe src='https://gfycat.com/ifr/IncompatibleDeadlyAntelopegroundsquirrel' frameborder='0' scrolling='no' allowfullscreen width='640' height='404'></iframe><p> <a href="https://gfycat.com/incompatibledeadlyantelopegroundsquirrel">via Gfycat</a></p>

One disadvantage of zone-based teleportation is how one chooses to select the appropriate room while teleporting. Generally each zone would be connected to surrounding zones. One reason to do this is so that less zones are available to the player, and they won't accidentally select a zone "behind" the one they wanted to go to, and become confused. This is especially important when using a head-position/gaze for selecting the destination zone, as it is less accurate.

<iframe src='https://gfycat.com/ifr/WelcomeIlliterateDarklingbeetle' frameborder='0' scrolling='no' allowfullscreen width='640' height='404'></iframe>

Not how in the above Vacation Simulator clip, I can't teleport down to the water area from the deck, even though it is "right there". I have to "follow the path" through the building to get to the zone. This makes sense because of the design of the level - there is no path connecting the two zones, while paths connect all other zones; but still feels like it *should* work for the player.

## GDC Talk by OWLchemy Labs.
The following GDC Talk includes an excellent analysis of zone-based and granular teleportation, as well as their pros and cons.

<iframe width="560" height="315" src="https://www.youtube.com/embed/q83f3sdQBBc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>