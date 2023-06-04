##########################
Working with files
##########################

.. contents::



Handling of files that can be read and written by this application
=========================================================================

I will explain the precautions for files that can be created and read by this application.

.. hint::
    These files are freely distributable.

    It can be read by dragging and dropping it on the WebGL screen.

project file
----------------------

    See :ref:`saveproject` and :ref:`openproject` for other explanations.

    :Extension: ``.vvmproj``

    Available storage and timing
        .. csv-table::
            :header-rows: 1

            App environment, timing, internal storage, device storage
            web app, first time, read/write, reading
            web app, second time onwards, read/write, write (as download only)
            Each OS version, First time, Read/Write, Read/Write
            Each OS version, 2nd time onwards, Read/Write, Read/Write
    

    Data related to project files
        Cast (object such as VRM)
            If there is a name, shape, and other special information of the object assigned to the timeline (role), it will be retained.

            The actual information of the object when opening the project file is:

            :Web application version: The file object itself is stored in the application
            :Each OS version: Only the file path, size and type are saved in the app
    
        motion data
            | The timeline (role) is the target. Retains the size and shape of the object at the time it was registered in the keyframe as reference information.
            | See :ref:`settingcast2role` for how to assign timelines (roles) and casts.
    
        Information about the project itself
            Although it is not particularly used, it is possible to retain the project name and description.

motion file
-------------------

    See :ref:`savemotionfile` and :ref:`openmotionfile` for a detailed explanation.

    :extension: ``.vvmmot``

    Motion data for a single timeline (roll). Retains the size and shape of the object at the time it was registered in the keyframe as reference information.

    If the object type matches, it does not depend on the actual cast (object). For VRM, the height difference is automatically calculated and reproduced.


pose file
----------------

    See :doc:`../man3/posing_save` and :doc:`../man3/posing_open` for a detailed explanation.

    :extension: ``.vvmpose``

    Only VRM can be used. Pose data when acquiring the timeline (roll) of the unit. It can be acquired and saved without the need to register it in a keyframe. The size and shape of the object at the time of acquisition are retained as reference information.

    It does not depend on the actual cast (object). The height difference is automatically calculated and reproduced.


object file
=============================

The object files that can be read by this application are his VRM, various 3D models, images, music and audio files.

are as follows: It also supports drag and drop on the WebGL screen.

* Vroid/VRM(.vrm)
* Other 3D objects (.obj, .fbx, .zip, .gltf ,.glb, .ply, .stl, .3mf)
* Image (.png, .jpg, .gif)

.. caution::
    Music and audio files do not support drag and drop.