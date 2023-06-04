.. index:: What is an animation project?

######################################
What is an animation project?
######################################


| You can freely animate objects that can be read with this application. The method of making animations is similar to MMD, MMM (MikuMikuMoving), and general animation creation software, so I think you'll get used to it in no time if you use it for a while.
| This application's original animation will be used for explanation under the name of "animation project".

.. figure::img/animation_1.png
    :align: center

|

.. note::
    * Please note that the animations in this application are unique implementations and are not compatible with the animation format used in MMD or Unity Editor. (We are also considering implementing a function to export to common formats in the future)
    * Animation data included in FBX can be played.
    * If you record later, you can save it in a generally playable format.

File format for animation used in this application
    It has its own format. There are three:

    .. csv-table::
        :header-rows: 1

        extension, overview
        .vvmproj, animation project (file that holds all information related to animation in this application).
        .vvmmot, motion data (animation information for each timeline (roll) in this application). In addition to VRM and OtherObject, animation information for cameras, 2D objects, and system effects can also be stored.
        .vvmpose, Pose data (information for only one frame in animation), VRM only.