.. index:: operating environment

########################
Operating environment
########################


:OS:
  Windows, macOS, Linux, ChromeOS [1]_
:Compatible browsers:
  | Edge, Chrome, Opera, Vivaldi, Firefox [2]_
:Traffic:
  | First boot: about 20-25MB
  | Stage changes/effect usage: about 30MB (only when used for the first time)
  | Immediately after the update・・・1KB to 25MB
  | Normal from the second time onwards: about 1 to 10 KB
  | * Web application version only

:memory:
  | 4GB or more of PC memory is recommended.
  | * The usage can be adjusted within the app within the range of 256MB to 4GB.
  | * Developed on a development PC with 8GB memory

:storage:
   A lot is enough [3]_

:Graphic Performance:
  | Check on the next PC
  | * PC with GTX 1060 to RTX3060 Ti
  | * Last Intel CPU model MacBook Air to M1 MacBook Air
  | * ASUS UX21A Notebook PC

:External access:
  | Google, jsdelivr, unpkg
  | * Purpose of style sheet and javascript library
  | * External access is not provided to areas other than the above.
  | * It does not have any function to send user data to the outside.

: Access to terminal (PC):
  | <Open>
  | * 3D object files such as VRM, image files, music files
  | * Movie files
  | * .vvmpose file, .vvmmot file, .vvmproj file
  |
  | <Save>
  | Screenshot
  | * Movie files
  | * .vvmpose file, .vvmmot file, .vvmproj file


.. [1] You can't use the PC version on ChromeOS.
.. [2] Firefox cannot do independent windowing of PWAs.
.. [3] Some files such as pose files and project files are saved in the app's internal storage, but they are all saved in the PC. It is not saved externally.

.. note::
  * Android and iOS are not supported according to Unity's WebGL specifications. (Actually, you can use it if you access it, but it is difficult to operate)
  * Communication volume is just a guideline. In principle, communication is only performed when loading or updating the application because it is PWA compatible.
  * Unity itself and additional libraries are not required for use.
  * Since it supports PWA (Progressive Wab App), it can be installed and used independently from the browser.
  * Windows, macOS, and Linux also have PC versions that run independently.
  * Browsers and extensions with mouse gestures may cause erroneous operations, so it is necessary to turn them off in advance or perform the key operation described later.
  * Please do not reload recklessly after the first time. When an update is ready, we will notify you on the app.

.. raw:: latex

   \cleardoublepage

