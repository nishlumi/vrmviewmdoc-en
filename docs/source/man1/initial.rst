##################
Introduction
##################


This app aims to be an MMD-like **VRoid (VRM) that allows you to easily create and play animations**. With this app, you can easily do the following things.

* You can make VRM take any pose and take a screenshot
* You can create animation by moving VRM from scratch without using MMD, Unity editor, Blender, etc.
 
We did not aim for a full-fledged 3D animation application, so it is not suitable for professional use. Animations created with this app can only be played with this app (for now) [1]_, but it should be much easier than creating them directly on the Unity editor. Also, since it is a web application, it can be used anywhere with a web browser. (Some features have technical limitations.)

.. [1] From ver 2.0, ``.anim`` format export is supported experimentally.

What is VRoid (VRM)?
========================


VRoid (VRM) is a new, easy-to-use 3D model standardized for use in VR applications and 3D games.
VRM has made a great contribution to the world as a 3D model standard and animation tool, and has more specifications than the famous MMD.
It is widely available and easy to use for general purposes. And the development and operation are actively continued, and the support side is also perfect.

It seems that the number of compatible apps is comparable to the MMD model, and now there are smartphone apps such as Android/iOS, PC and VR device applications, etc.
We are expanding our activities in a variety of ways.

It seems that it was originally created with the avatar of a VR app in mind, but it is also possible to animate it in 3D with the VRM alone.
If it is a game creation environment called Unity, even at an individual level, you can move VRM limbs with Unity's animation function
You can pose and animate.

However, it is quite difficult to introduce Unity, introduce a VRM loading library, and handle Unity's animation function.
If you don't use assets such as VeryAnimation that make it easier to create animation (even if you do), the threshold will be high.

Given the current situation, the biggest disadvantage of VRM is that there is still little software comparable to MMD as software.
I personally think so. (Even if there is, it is troublesome to have to create motion with exaggerated tools such as Unity and other animation tools...)

Therefore, in this application, I myself tried various animation creation support assets such as VeryAnimation in Unity and gave up,
So I decided to contribute to the world by creating an easy-to-use VRM operation library and animation creation application.


.. caution::
  There is no relationship between the VRM, the characters in the photos, and the game works displayed in this manual and this application itself. We are only using it as a sample by creating it on our own under the secondary creation. note that.