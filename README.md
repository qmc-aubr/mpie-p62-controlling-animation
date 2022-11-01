# Practical 6.2: Controlling Animations in Unity

In the second lecture this week, we saw how to use state machines to control potentially complex combinations of animations in response to input and other events in an environment. We also saw how state machines can be implemented in Unity using an Animation Controller. In this practical, you’re going to put these ideas into practice by controlling multiple animations on a character.

By the end of this practical, you’ll be able to control a character, and most other kinds of, animations in Unity using an Animation Controller. In particular you’ll be able to:

-	Import animations into Unity and attach them to a model (in this case a character)
-	Create a state machine that defines the order those animations can play in
-	Control that state machine by setting the value of parameters in response to inputs and other information about the state of the environment.

These instructions assume you’ll be using the adventure game scene from previous practical classes as the basis of this practical. However, you might also choose to use the terrain you created in week 2, should you wish to see how an animated character might behave in that environment.

## Task 1: Downloading and adding the third person character controller 
In the practical today you’ll be working in the adventure game scene from a previous practical. Therefore, to get started, open up this scene. When doing this, you might wish to save a copy of the scene as it was at the end of the last practical you used it in, because we’ll be changing how you interact with it quite a bit.

The current adventure game scene is played with a first person character. In this practical, we’re going to change this so that the scene is seen from a third-person view, which allows us to see the animations we’re going to add to a character representing the player.

I’ve provided a simplified third person character controller that you can use as a starting point for the practical. To add it to your scene, complete the following steps:

1. Download the third-person-controller.unitypackage within this Git repository
2. Delete (or disable) the “FPSController” game object from the hierarchy
3. Drag the “ThirdPersonController” prefab from the “Animation Practical Assets” folder into the scene

Once you’ve done this, press play and explore the scene using the new third person character controller. You should see it has the following controls:

-	Mouse to look around and turn
-	Up & down arrows to walk forward and backwards
-	Shift to run
-	CTRL to walk slowly (and as you’ll see later crouch)

## Task 2: Downloading and adding a character with an idle animation:
You might have noticed that the ThirdPersonController prefab doesn’t actually show a character. Rather, the player is represented in the scene using a simple capsule shaped object. In this task, we’re going to change this by downloading a character, and an associated animation, and replacing the capsule with them.

We’ll be sourcing our characters from https://www.mixamo.com/. This is a service that you can access with your Adobe account (university login). It provides a library of characters and animations that can be applied to them.

To complete the task, you should log into Mixamo and:

1. Choose a character that you would like to feature in your scene (when you’ve found one you like, simply click on it and choose “use this character”).
2. Search for an idle animation and apply it to the character (click on the animations tab, search for “idle” and then click on the animation to see it applied to your character).
3. Download the character and animation to your computer (you should save the character as an FBX Binary with skin applied and animations at 30fps).

To complete the task, see if you can replace the white capsule on the ThirdPersonController, such that you see the character move around the environment in its place when playing the scene.

## Task 3: Adding and playing an idle animation
You might have noticed that your character just floats around the scene like a statue. Let’s make things more realistic by having them perform the idle animation you selected on Mixamo.

Before we do this, we’re going to give that animation a new name. Mixamo calls all of its animations “mixamo.com”, which can get a little confusing when we start working with multiple animation states. To fix this, expand the prefab (click on the little arrow) and click on the asset represented by the little turquoise triangle (Unity’s icon for animations). Choose edit in the menu that appears in the inspector and see if you can find the option for changing its name to something more meaningful (e.g. “Idle”).

Next we want to add this newly named animation to our character so it’ll play when the character stands still. To do this, simply drag the animation asset into the inspector for your character in the scene. When you do this, a new component should appear called an “Animator”. We will use this component to control this and other animations throughout the rest of the class.

To complete the task, press play and observe what happens.

## Task 4: Controlling animations with the animation controller

When you pressed play you should have noticed that the idle animation played just once before the character returned to being stationary. Not ideal! In this task we’re going to see how to use the AnimationController to fix this.

To access the Animation Controller for the character, look at the Animator component you created earlier. You should see that its got a parameter called “Controller”. If you click on the value in this parameter’s box, the Animation Controller user interface that we saw in the lecture will appear. 
Do this, and look at the state machine. Can you work out what it does and why it makes the idle animation play just once when the game starts?

To complete the task, see if you can edit the state machine such that the idle animation plays on a loop all the time. To find the solution to this task, you should double click on the animation state representing the idle animation. Explore the options that appear in the inspector for configuring the animation. Is there one that’ll make it loop?

## Task 5: Creating a transition between animation states
You now should have a character with a looping idle animation, which is great until our character moves. At this point, we might want to play a walking animation instead. In this task, we’re going to try and do that.

To get started with this task, go back to Mixamo and download a walking animation. When downloading this animation you need to do two things differently this time:

-	Make sure you click the “in place” checkbox in the options that appear on the right (it’s very important you check this, as this will make character control a lot simpler for now)
-	Choose “without skin” when downloading the character. This will give you a file containing just the animation, rather than downloading the character’s 3D model again as well.

Now you’ve got this new animation file, see if you can do the following:

1. Import the new animation into Unity and add it as an additional state in the animation controller
2. Create a transition between the idle state and the walk state (you can make new transitions by right clicking on the state you want to transition from, choosing “Make transition” and then clicking on the state you want to transition to).

Press play and see what happens, does it do what you expect?
