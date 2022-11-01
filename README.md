# Practical 6.2: Controlling Animations in Unity

In the second lecture this week, we saw how to use state machines to control potentially complex combinations of animations in response to input and other events in an environment. We also saw how state machines can be implemented in Unity using an Animation Controller. In this practical, you’re going to put these ideas into practice by controlling multiple animations on a character.

By the end of this practical, you’ll be able to control a character, and most other kinds of, animations in Unity using an Animation Controller. In particular you’ll be able to:

-	Import animations into Unity and attach them to a model (in this case a character)
-	Create a state machine that defines the order those animations can play in
-	Control that state machine by setting the value of parameters in response to inputs and other information about the state of the environment.

These instructions assume you’ll be using the adventure game scene from previous practical classes as the basis of this practical. However, you might also choose to use the terrain you created in week 2, should you wish to see how an animated character might behave in that environment.

# Task 1: Downloading and adding the third person character controller 
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
