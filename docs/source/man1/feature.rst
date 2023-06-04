###############
feature
###############

.. index:: Available (features)

Available
------------------

The main things you can do with this app are as follows.
    * Read VRM files (also supports VRM height information display)
    * VRM bone operation (Only IK operation for now, so that you can experience a steady and easy operation)
    * Loading and transforming 3D model files such as FBX, Obj, and STL [1]_
    * Read and transform 2D images such as jpg, png, and gif
    * Camera, light, effects, post-processing (screen effects) available (Unity feature)
    * Audio support (MP3, wav) [2]_
    * Move VRM and other objects in tandem
    * VRM only, poses can be saved/loaded in pose files
    * Animation can be created (using a simple timeline and keyframe method)
    * Ability to save and load animations as project files
    * You can freely change the screen size of the WebGL part
    * Save current screen as screenshot
    * The current screen can be recorded and saved as a video (Of course, animation can also be saved)
    * Supports multiple languages (Japanese, English, Esperanto, others to be added in the future)
    * Google's MediaPipe can automatically detect and reproduce poses from camera images with AI [3]_
    * Supports subtitle editing with Web Video Text Track Format (WebVTT) (from ver 1.2.0)


.. [1] All formats supported by TriLib2 (https://ricardoreis.net/trilib-2/)

.. [2] Some audio effects are not supported by WebGL in Unity.

.. [3] Because it is an experimental feature, it may not be a perfect reproduction.

|

.. index:: not available (feature)

Not available
--------------------------

The following is what this app cannot do in the current version (2.0.0).
   * Due to Unity's specifications, each OS's native rendering is comparable to that of consumer machines (WebGL environment has much lower rendering performance than those)
   * Opacity of 3D objects (unable to express due to Unity's WebGL specification, 2D objects can)
   * Posing by directly rotating each bone of the VRM (so-called FK. Same meaning as the second thing you can do)
   * Read Unity, MMD/MMM animation files, motion files, etc. (animation data included in fbx can be read)
   * Read VRoid from VRoidHub (VRoidSDK is only C#, so it is impossible from HTML for security reasons)
   * Editing, processing and saving VRM (not supported because it is not the purpose of this application)
   * Directly read VRM, FBX, Obj, etc. on the net (there are restrictions because it is a web application)
   * Loading ogg (Ogg Vorbis) audio files (WebGL in Unity does not support ogg streaming in the first place)

.. note::
   * In the future, if the assets and libraries used are upgraded, it may be possible to use this application as well. note that.


.. raw:: latex

    \cleardoublepage