.. index:: keyframe registration window (screen configuration)

#####################################
Keyframe registration window
#####################################

.. |keyframe1| image:: ../img/screen_ribbon_animation_keyframe1.png
.. |keyframe2| image:: ../img/screen_ribbon_animation_keyframe2.png

It is displayed by right-clicking anywhere on the ribbon bar (control-click or two-point tap for macOS) or pressing the ``Register keyframe`` button on the animation tab. Here you can select properties and bones that you want to register in keyframes.

When you press the ``Register keyframe`` button in this, it will actually be registered.

.. csv-table::
    :header-rows: 1

    VRM, non-VRM
    |keyframe1|, |keyframe2|

:Register Keyframe: 
    Registers the state of the currently selected object to the current keyframe. If you register again at the same keyframe position, it will be overwritten.

: top right toolbar:
    For use in future versions. I don't use it yet.

    Deselect all bones from the left, select all bones, select IKParent, select upper body, select lower body



:Contents to be registered: 
    Select the content to be registered in the keyframe from Move, Non-Move, or Property.

:Bone to register:
    You can check the bones (IK markers) registered in the keyframe. This number differs between VRM and non-VRM.
    
..
     * You cannot press Select Upper Body or Select Lower Body except for VRM.
     Since VRM exists for each part of the body, it registers only the movement of the RightHand, for example. You will be able to

     Since there is only one IK marker other than VRM, it is meaningless to uncheck it and register anything other than movement/movement.