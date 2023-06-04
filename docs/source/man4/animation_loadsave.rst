.. index:: Loading and saving animations (animation projects)

##########################################
Loading and saving animations
##########################################

.. contents::




.. index:: save motion (animation project)

.. _savemotionfile:

Save to motion file
=====================================

.. index:: save motion in .vvmmot format

This application's original format .vvmmot
----------------------------------------------------

You can save motion data for only one roll to a file. You can print for all roles.

1. Click ``Settings`` on the ``Animation`` tab of the ribbon bar.

2. Open the ``Manage Roles`` tab.

3. Select the row of the role you want to save.

4. Click ``Save Motion to File`` on the toolbar.

.. image::img/loadsave_1.png
    :align: center

|

5. Enter the file name and press the ``OK`` button.

:Save format:
    **.vvmmot**

    * Although it has its own extension, it is actually just a JSON format file. You can read it even if you change the extension to .json. Operation is not guaranteed if incorrect data is read.

.. index:: Notes on reading and writing motion files

.. warning::
    **Pay attention to the physique of the VRM that creates the motion**

    When creating motion data with VRM, if you replace it with a VRM with a different height or physique in the middle, there will be a gap in the ground and each part. Be sure to complete the motion creation with the same VRM.

    example:
        1. Create the motion halfway with a 160cm VRM and save it in a file
        2. Load the vvmmot file into a 155cm VRM on another day and create the continuation of the motion
        3. On another day, load the vvmmot file into a 140cm VRM and play the motion

        In this case, 3's 140cm VRM causes the whole body to float and move unexpectedly during motion.

.. caution::
    After loading the motion, if you want to save it as a motion file again, **must** register each keyframe once.

    Immediately after loading the motion, the current VRM's height information and the height information of another VRM as reference information in the motion are mixed in the timeline (roll).

    | By registering the keyframe again, the motion will be registered as the current height and physique of the VRM.
    | (When registering, it is not necessary to move the pose etc. You can press the register button as soon as the frame number is selected and the object such as VRM reproduces the motion)

    This has the same meaning as the above problem "Pay attention to the physique of the VRM that creates the motion".


.. index:: save motion in .anim format

General format such as Unity
-----------------------------------

1. Click ``Settings`` on the ``Animation`` tab of the ribbon bar.

2. Open the ``Manage Roles`` tab.

3. Select the row of the role you want to save.

4. Click ``Export as a generic motion file`` on the toolbar.

5. Click the desired format menu.

.. image::img/loadsave_d.png
    :align: center

|

1. Enter a file name and press the ``OK`` button.

:Save format:
    **.anim**

.. note::
    An .anim file is an AnimationClip file that can be read as-is in Unity.

.. warning::
    As of ``ver 2.0.0`` of this application, only motions of Humanoid's Animator are supported. .bvh is still under test operation, so it is not guaranteed to work. please note that.

    The .anim file cannot be read again by this application.

| 

.. index:: load motion (animation project)

.. _openmotionfile:

load motion file
=================================

A motion file ``.vvmmot`` can be read and reflected in a specific role (timeline) in an animation project.

1. Click ``Settings`` on the ``Animation`` tab of the ribbon bar.

2. Open the ``Manage Roles`` tab.

3. Select the row of the role you want to load.

4. Click ``Load Motion File`` on the toolbar.

.. image::img/loadsave_2.png
    :align: center

|

5. Select the target file and it will be loaded automatically.

**Alternative method**

1. Select the cast assigned to the role you want to apply the motion to.
2. Drag and drop the ``.vvmmot`` file from Explorer etc. to the WebGL screen.

.. note::
    * Role types must be the same.
    * Please note that if motion data already exists, it will be overwritten (handle new registration after deleting all).
    * If the number of frames is more than the maximum number of frames in the current project, it will be cut to the maximum number of frames. It is recommended to expand the number of frames to some extent in advance.
    * When dragging and dropping, only ``.vvmmot`` extension is valid. (Cannot be opened with ``.json``)
    * When dragging and dropping, the currently selected cast must be assigned to some role. (If you do it from the project settings screen, it will be applied directly to the role, so there is no problem even if the cast is not assigned.)

.. hint::
    The time (duration) of each frame that motion takes is independent for each timeline (and even for each frame), so loading it into an existing project will not affect other timelines.

|

.. index:: Save Animation Project (Animation Project)

.. _saveproject:

Save animation project file
===================================================

Once you have created an animation project, you can save it as a file.


:Saved content:
    * Timeline (including all keyframes)
    * Information on all roles
    * Other settings on the animation project
    * Materials in the project (including actual files)

1. Click ``Save`` from the ``Animation`` tab of the ribbon bar.

.. image::img/loadsave_3.png
    :align: center

|

2. Click ``Save`` or ``Save As``.

.. image::img/loadsave_4.png
    :align: center

.. note::
    Each OS version has a ``Terminal`` menu that allows you to save directly to your PC.

3. For ``Save As``, enter a name in the input dialog.

The animation project will be saved in the dedicated storage inside the app or on your PC.

.. note::
    * In the case of **Save**, a confirmation message will be displayed if the project already exists.
    * After saving, a notification message will be displayed on the upper right.


|


:Save format:
    **.vvmproj**

    * Although it is a unique extension, it is actually just a JSON format file.


.. |projopen| image:: img/loadsave_5.png


|projopen| To download to a PC or terminal, click ``Open`` to display the internal storage dialog, then click this button on the toolbar.


|

.. index::
    Open Animation Project (Animation Project)
    Restoring the actual object
    Behavior after opening an object

.. _openproject:

Open animation project
=================================

You can read the saved project file.

1. Click ``Open`` from the ``Animation`` tab of the ribbon bar.

2. ``From File`` opens the OS file dialog, and ``From Internal Storage`` opens the internal storage dialog within the app.

.. hint::
    You can filter projects using the search box at the top of the list.

    .. image::img/loadsave_e.png
        :align: center

3. After selecting the target project, press the ``OK`` button.


What is restored
    * Timeline (including all keyframes)
    * Information on all roles
    * Other settings on the animation project
    * Materials in the project (including actual material files)
    * Cast entity (actual object file)

.. admonition:: Differences between the web application version and each OS version

    The actual behavior when opening a project file differs between the web application version and each OS version. If there is a VRM or 3D model file used in the project, it will be loaded as follows.

    Web application version
        Reads files saved in the app (a special location prepared by the browser in the terminal) (not saved on the server of this app).

    Each OS version
        Only meta information such as file path and file type is stored in the app. Refer to the meta information and open and read the VRM and 3D model files in the actual terminal.

    In the project file, there is a property called ``path`` that indicates the file path of each cast, but it is not the actual file path. Even if you edit the file path directly there, the file targeted for that cast will not be loaded.

    This is due to the fact that HTML and javascript are used, and as a security measure, only files that have been opened once are allowed to be read automatically**. please note that.

.. admonition:: restore the actual object

    The casts (objects) assigned to each role are also automatically opened and restored as much as possible.

    | However, only objects that meet the following conditions.
    | Objects that do not match will not be loaded and no cast will be assigned to the corresponding role. Playing the animation does not move the role, so you need to operate " :ref:`settingcast2role` ".

    * Basic shapes (OtherObject), Camera, Light, Effect, Text
    * Object files (VRM, OtherObject, Image, UImage) stored in the app history
    * Object files that are less than or equal to the size specified in the settings


    For VRM and other objects, the criteria for assigning roles are different. If they match each other, the assignment will be completed automatically and you will be able to operate it immediately on the app.

    .. csv-table::
        :header-rows: 1
        :align: center

        Kind, Criteria
        VRM, title of VRM
        OtherObject, filename
        Image, filename
        UImage, filename
        Other than above, automatically depending on type

    * Audio is not included here.

.. caution::
    The contents of previously opened projects are reset.

    Settings ``Do not load files larger than this size automatically when the project is opened.`` If is a valid size, each oversized object will skip loading when opening an animation project. In this case, open the corresponding object file later. Restoring rolls and casts is described above.



.. index:: Create a new project (animation project)

Create a new project
===============================


Create a new project. It is not necessary when starting the application. Use this when you want to start over an already open project.

1. Click ``New`` from the ``Animation`` tab of the ribbon bar.


What New Creation Does
    * Removed all animation projects (except SystemEffect, BGM, SE, Stage)
    * Delete all loaded VRoid/VRM, each object


|

.. index:: Manage project files (animation projects)

Manage project files
====================================

You can manage saved project files in the internal storage dialog.

1. Click ``Open`` from the ``Animation`` tab of the ribbon bar.

.. image::img/loadsave_6.png
    :align: center

|


2. The Internal Storage dialog will open.

|

open from file
---------------------

1. Click this button on the toolbar.

.. image::img/loadsave_7.png
    :align: center

|


1. Select and open the file with the desired extension .vvmproj or .json.

* Operation is not guaranteed if incorrect data is read.

|

rename
----------------

1. Click this button on the toolbar and enter a new name.

.. image::img/loadsave_8.png
    :align: center

|

Delete from internal storage
-----------------------------

1. Click this button on the toolbar.

.. image::img/loadsave_9.png
    :align: center

|

.. note::
    All materials linked to the project will also be deleted from within the app.


.. index::
    Backing up project files (animation projects)
    backup
    Restore backup

Back up your project files
=========================================

You can periodically back up the currently open project.

1. Open the app settings.
2. Check ``Back up project`` in the Application tab.
3. In Backup Interval, specify how often you want backups to occur automatically, in minutes.

.. image::img/loadsave_b.png
    :align: center

4. Open the internal storage dialog and it will be saved as ``%BACKUP%``.

.. image::img/loadsave_c.png
    :align: center

|

.. admonition:: What triggered the backup

    Backups are subject to action when you:

    * changed maximum number of frames
    * Registered/deleted keyframes
    * Pasted keyframes from the clipboard
    * Cleared the contents of the timeline
    * Removed roles and timelines

    Conversely, as long as you don't register a keyframe, you can continue to do new operations without overwriting the old backup.


If an unexpected situation occurs and the app terminates or becomes uncontinuable, opening ``%BACKUP%.vvmproj`` will allow you to immediately resume from the previous state.

.. warning::
    After opening the backed up project file, change the file name when saving again. File names containing ``%BACKUP%`` cannot be saved.