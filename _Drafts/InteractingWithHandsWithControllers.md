# Interacting With Hands With Controllers
Virtual worlds give us hands, but the real world has us holding a controller.

How do we make this work?

See notes on the Display of Hands.

## When to assist and when not to assist
Assist the player, who is forced into clumsyness, as much as possible. 

## Avoid Finger-Precise Motion from Controller Position
I find extending a pointer finger and pressing a button is one of the most annoying things to do in VR. It works fine depending on the position of the button — if I am pushing it with my finger perfectly perpendicular to the button. If the button is in any other position, however, I would (in the real world, and as promised by the skeuomorphic design and hand representation) would move my hand near the button, and bend my finger to press it. Like how I’m typing right now. My hand isn’t extending straight up above the keyboard, pointing down at it.

Humans are far more accurate with moving the tips of our fingers than moving our hand. Controller tracking does not track the tips of our fingers (buttons and joysticks aside). If you ask me to push a small button with the tip of the finger, but then make me push the button buy moving my entire hand - that’s both annoying and presence-breaking.

If you want me to have finger-precise input, give me a controller or virtual tool or whatever excuse to map that input to a joystick, button-press, or trigger on the controller. In other words, map finger-tip-presice virtual input to finger-tip input from the controllers, and map hand-position input from the controllers to hand-position interfaces in the game.

(Circling back to an above point, this is one of the reasons that not showing hands, at all, is a decent solution. The trigger of the controller maps well to the trigger of a gun, and allows for precise and accurate input. You can invent new tools for your experience that map well tio controller input. Humans are good at learning tools, while hands should behave as we expect.)

This is why virtual input works well when you’re smashing giant buttons with your fist, or pulling on ceiling-fan cords. I’ve seen a few implementations of switches in VR, where you smash them with your fist, and they flip their state subtlety. It’s weird and uncomfortable. One might as well make it a giant handle to pull. The good news is those examples at least do respond to being “smashed by a fist”.