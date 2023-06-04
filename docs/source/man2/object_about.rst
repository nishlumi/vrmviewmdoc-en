.. index:: object (object that can be handled)

##################################
Objects that can be handled
##################################


From here, we will explain in detail the properties of each object and how to actually operate VRM and other objects on the WebGL screen.

The objects that can be handled by this application are defined as follows.


.. list-table::
  :header-rows: 1

  * - kinds
    - explanation
  * - VRMs
    - This is the main 3D model object in this application.
  * - OtherObject
    - Other 3D objects such as FBX, Obj, STX. [1]_
  * - Light
    - It is a light object by Unity standard function.
  * - Camera
    - Camera object by Unity standard function.
  * - Effect
    - Effect object by Unity standard function.
  * - Image
    - Load 2D images such as jpg and png as 3D objects. The handling is equivalent to OtherObject.
  * - Text
    - Not a 3D object. It is a text object that is displayed on the WebGL screen mainly for dialog display and user interface purposes.
  * - UImage
    - Similar to Text, it is a 2D image used primarily for user interface purposes.
  * - SystemEffect
    - Screen effect.
  * - Audio
    - An audio object used as BGM or SE.
  * - Stage
    - Handle terrain and stages such as the ground, sky, and wind.

.. [1] All formats supported by TriLib2 (https://ricardoreis.net/trilib-2/)

.. note::
    Text and UImage cannot be treated as 3D objects, but they can be moved and rotated.