# On The Display of Hands

Hands are deeply personal things. This is a fact I know as well as the back of my hand. In VR, many verbs operate around the hand. Pointing, grabbing, selecting, pushing, throwing, and so on.

Creating interfaces that are intuitive is done easily with hands. We show the user something they recognize as interactable, like a button, a switch, or a rope. Then show them a virtual hand where their real hand is. 

But how do we show them where their real hand is? There are a lot of elements to consider.

## Tracking Technology
 There are three main types of hand tracking technologies: Optical or Sensor based, Gloves, and Controllers. Sensor-based hand trackers allow the user to have their hand represented without having to hold or wear anything, and many technologists believe it’s the “way of the future” thanks to a low barrier to use.
 
 Gloves, going back to Jaron Lanier’s DataGlove, have had a long history in VR development. They allow us to get past technological limitations of sensor-based tracking without asking the user to hold anything, and can have haptic solutions built into them.
 
 Controller based solutions are the most common. The biggest drawback is asking the user to hold a controller. It’s difficult to throw things, open ones hand, grab and let go of items, and other ‘open-hand’ interactions while remembering to not actually open ones hand all the way. Users get used to never letting go of the controllers, and when they leave VR, they have trouble putting them down. It is a challenge to infer hand/finger position from a gripped controller as well. They are ever-present and unable to be forgotten about, but allow for some interactions - like the timing of a button press - that users can complete with greater accuracy than with other technology, thanks to user familiarity. 
 
 The rest of this document will assume controller-based systems for hand tracking.
  
## Do you need hands?
The fact that we need to show the controllers in VR appears to be an obvious question: of course. It doesn’t get enough consideration. Think deeply about whether an experience ever actually needs to show hands as hands. 

For many experiences where the main interaction is through a tool (say, a gun), a hand is probably unnecessary. We can show a model of the controller while in menus or to confirm tracking, and during the experience itself, a gun should just be a gun. No need to have a hand grip it. The player holds a controller, in VR a tool floats where that controller is and they use it. No thought required. This is often a preferred solution for many games that insist on showing hands anyway.

## Show A Controller
To abstract from the previous point, one does not need to represent hands in space when they can just represent the controller. Either through a realistic model of the controller the player is using, or through a version of the controller that looks similar enough one could point out buttons on it, but otherwise fits into the world of the experience.

This is a good solution, requires almost no teaching to the player, doesn’t break immersion or presence, and is generally far easier to implement then hands. Consider it seriously.

## Degree of realism
First and foremost, the representation of hands should fit into the world. If you have a realistic looking world, your hands should be realistic. If you have a cartoony worlds, the hands should match. 

The closer we get to “real hands” visually, the closer we need the hands to behave like the users real hands in order to not break a feeling of presence. Sort of an ‘uncanny valley’ of hands, conceptually.

As a rule of thumb, consider the simplest version you can get away with in your world, and go from there. 

## Degree of realism in representation
Ways to represent hands, in increasing degree of realism.

1. Abstract representation, non-diagetic (semi-transparent orbs)
2. Abstract representation, diagetic (blocks)
3. Simple cartoony gloves (perhaps less than 5 fingers)
4. Realistic gloves (5 fingers)
5. Model of Hands (5 fingers)
6. Realistically modeled  Hands
7. Pass-through/Mixed reality of actual users hands

Each of these have their own advantages and disadvantage. We will circle back on this list after talking about some of the properties of “hand realism”.

## Pass-through vs Collision
Does the hand go through Solid virtual objects, or does it collide and attempt to move around them?

Most solutions tend to use let hands pass-through virtual objects as a matter of technical implementation. 

One decent trick is to briefly collide while the real-world hand is close-enough to a solid surface. Great for picking things up off to tables without being reminded the table isn’t real. If the hand moves too far from the virtual hand, it snaps back to the real-hand location (inside an object, wherever). 

This trick keeps you from constantly seeing your hands intersecting virtual objects, and subtlety reinforces the solidity of the world without the further dissociative issue of virtual hands and real hands not matching.

It takes fine-tuning, as if a virtual hand doesn’t move when a real one does, that too is presence-breaking. Enabling a vibration or other haptic feedback to smooth over this interaction can be helpful.

## Hands vs. Gloves
Hands need to look like hands. For the most part, we don’t know what the users actual hands look like. It’s awkward being in somebody else’s hands. 

Don’t turn to gloves just yet. Can you use that uncanniness as a storytelling tool? Robotic hands like in The Lab or Tea For God are very cool, I’m a robot! It helps enhance immersion, not break it, so long as the version of the hands is in-line with the world. The visuals are not *my* hands and that takes away a degree of presence - if I am trying to imagine myself in this world. But what if I am not myself, I am role-playing as someone else? A lot of storytelling and role-playing distance can be given by carefully considering the hands. Hands are, of course, very personal. A player can examine their hands and learn about themselves. Are they tough, calloused, dainty, hairy, or scarred? Are they just a skeleton? What race is the character? Are they married? What does their jewelry say about them?

If the player is not playing as a character, but ‘just themselves’, gloves are a way to get around a lot of these tough design decisions. Gloves still can communicate a lot about the character and world, from cartoony to science fiction.

The gloves should be realistic to the world. In Vacation simulator, you have large cartoony gloves - and so do all of the AI. It’s a glove-wearing world, and consistently so. 

## IK, Hand-Hole, or Solid
How do you deal with the end of the hand? Do you attempt to calculate the players likely arm position, and show them an arm? (See: *Tea For God* and *Half & Half*). 

What about the hole? Generally for hands, making the end solid is preferrable to an empty hole, which works fine for gloves. Nobody wants to be holding skin-gloves, that’s weird.

<iframe src='https://gfycat.com/ifr/GrimyJaggedGlobefish' frameborder='0' scrolling='no' allowfullscreen width='640' height='404'></iframe>
*In Garden of the Sea, the hands are solid and perfectly black, made to look like holes but without receiving light or shadows. Also note the IK is simple, one can close or open the hands, and that's it, no individual finger IK.*

How the end is designed should be consistent with the world - a horror game could remind you of your flesh, blood, and bones. A solid flat perfect-black surface may work in a cartoony game but seem out of place in a hyper-realistic world. That world may be better to design a darkened mostly-flat nub that is textured and receives shadows.

You want the player to forget about it if it doesn’t matter, but if they do notice it, you want it to contribute to the world building.

I pitched a design (I never made this game) where you play as a ghost inhabiting different dead bodies in order to “re-love” their last moments to solve a crime. (I had recently played Return of the Obra Dinn, a game better than any I would have ended up making). My plan for hands was to use them as a main storytelling device. In one case, the victim would have been dismembered, and when you inhabited their body, instead of arm-IK, you got the dismembered floating hand, bloody and with a bone sticking out. That was the plan, any way. It would have made a nice comedic surprise. 

## Arm Realistic IK vs Abstracted
For arms, you have further decision to calculate the likely arm position of the player, or to just show some other version of arms. Consider Half & Half, which doesn’t bother with IK. 

## Tomato Presence
*see Owlchemy Page*
## Finger IK
Finger IK is one of the toughest parts of designing hands, One can interpret from various button presses/touches/controller information what pose the hand is in, and show it accordingly.

The Oculus Touch controllers were released with a lot of excitement about these features.

In practice, it’s doesn’t work so well as pose-matching. Instead, the player has to learn new poses that are *similar* to the one they are trying to match. Hold the controller but extend the pointer finger to point, sure enough. Stop resting the thumb on the joystick (which is natural and a player forgets they are doing) in order to give a thumbs up.

Players, particularly those used to controller interfaces, have never really before been asked to consider if they are touching or not touching a button as an input. Some players hover their finger, rest it securely on a button, or keep a finger touching a few buttons and “roll” the finger around to press them. The oculus touch controllers ask players to pay attention to an attribute previously ignored, and forget common comforts, in order to gain a wider variety of hand poses the player can do.

Because of this, the poses tend to be learned just like any other controller interface, and the dreams of them being more “natural” are... sort of there. It works alright, once you are used to it. I find it annoying for key interactions - if I cant push a button because my hand is in the wrong pose because I didn’t lift my thumb *off* of the joystick, that’s troublesome. The interface - like a button - should accept as many poses as possible. A button should accept any pose, I should be able to just slap it with my hand, and not have to remember how to extend a pointer finger.

## Avoid Finger-Precise Motion from Controller Position
I find extending a pointer finger and pressing a button is one of the most annoying things to do in VR. It works fine depending on the position of the button — if I am pushing it with my finger straight perpendicular to the button. If the button is in any other position, however, I would (in the real world, and as promised by the skeuomorphic design and hand representation) would move my hand near the button, and bend my finger to press it. Like how I’m typing right now. My hand isn’t extending straight up above the keyboard, pointing down at it.

Humans are far more accurate with moving the tips of our fingers than moving our hand. Controller tracking does not track the tips of our fingers (buttons and joysticks aside). If you ask me to push a small button with the tip of the finger, but then make me push the button buy moving my entire hand - that’s both annoying and presence-breaking.

If you want me to have finger-precise input, give me a controller or virtual tool or whatever excuse to map that input to a joystick, button-press, or trigger on the controller. In other words, map finger-tip-presice virtual input to finger-tip input from the controllers, and map hand-position input from the controllers to hand-position interfaces in the game.

(Circling back to an above point, this is one of the reasons that not showing hands, at all, is a decent solution. The trigger of the controller maps well to the trigger of a gun, and allows for precise and accurate input. You can invent new tools for your experience that map well tio controller input. Humans are good at learning tools, while hands should behave as we expect.)

This is why virtual input works well when you’re smashing giant buttons with your fist, or pulling on ceiling-fan cords. I’ve seen a few implementations of switches in VR, where you smash them with your fist, and they flip their state subtlety. It’s weird and uncomfortable. One might as well make it a giant handle to pull. The good news is those examples at least do respond to being “smashed by a fist”.

