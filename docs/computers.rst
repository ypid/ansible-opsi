Experiences with different computer models
==========================================

.. contents::
   :local:
   :depth: 3

In this section the author documents his experiences with various computer
models he has worked with and how to best configure them for a school
environment.

System firmware setup
---------------------

TODO
~~~~

* Is it possible to import system firmware settings using the GUI software thingy that the OEMs provide?


Reasons for changing certain settings
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Build-in cameras
""""""""""""""""

The author of this documentation and teachers he has worked with believe that
in a school environment the number of occurrences where a build in camera would
be actually useful to be very limited. Thus cameras are disabled in the
system firmware settings. Additionally, consider convening the cameras
with electrical tape just to be sure.

Build-in microphone
"""""""""""""""""""

Most system firmware settings don’t give you control over disabling the build
in microphone independently from the audio subsystem.

System firmware for which this has been verified to work:

* HP ProBook 6560b

Without hardware modifications, there seems to be no easy and reliable fix for that.


I/O MMU virtualization
""""""""""""""""""""""

Fujitsu seems to disable this by default. Reason is unclear to the author and
it might come in handy when deploying desktop virtualization and as security
feature (currently unused by common proprietary OSes). So it was decided to
enable it.


Fujitsu
-------


ESPRIMO P556
~~~~~~~~~~~~

Infos
"""""

* WOL only gets enabled after the system has been put into ACPI G3.

System firmware setup
"""""""""""""""""""""

* Enter setup via F2
* "Security" → "Administrator Password" → set password
* "Advanced" → "Trusted Computing" → "HashPolicy" → "SHA-2"
* "Power" → "Power Failure Recovery" → "Always Off"
* "Power" → "Low Power Soft Off" → "Disabled"
* "Boot" → "Boot Menu" → "Disabled"
* "Boot" → "Boot Removable Media" → "Disabled"
* "Boot" → "Boot Option #1" → NIC
* "Boot" → "Boot Option #2" → data storage device


Fujitsu Lifebook E556
~~~~~~~~~~~~~~~~~~~~~

Infos
"""""

.. warning: WOL does not work!

* Opsi boot image needs a more recent Linux Kernel to recognize the ethernet NIC. Works successfully with Linux 4.4.
  Check: http://download.opensuse.org/repositories/home:/uibmz:/opsi:/opsi40-experimental/Univention_3.2/amd64/
* ``opsi-linux-bootimage`` as of 20160608-1 fails somehow to boot/install the OS when the lid is closed.
  And yes, I am a 100% positive on this. I installed 28 of those machines so I
  guess you could call this representative.  I did not yet verify if the
  problem also occurs with other models with the same version of
  ``opsi-linux-bootimage``. Needs testing.
* Can be ordered without build in camera :)
* WOL does not seem to work. Even in AC mode. NIC link is shut down in S5. Only works right after leaving the firmware setup with save and power off.
  Might be related: http://support.fujitsupc.com/CS/Portal/supportsearch.do?srch=FAQ&Series=E%20Series&Model=E556&ProductType=Notebook%20PC#wakeonlan

System firmware setup
"""""""""""""""""""""

* Enter setup via F2
* "Advanced" → "CPU Features" → "Intel(R) VT-d" → "Enabled"
* "Advanced" → "Miscellaneous Configurations" → "Wake up on LAN" → "Enabled"
* "Advanced" → "Miscellaneous Configurations" → "Wake up on LAN" → "On Battery" → "Disabled"
* "Security" → "Set Supervisor Password" → set password
* "Security" → "Boot from Removable Media" → "Supervisor Only"
* "Security" → "Boot Menu" → "Disabled"
* "Boot" → "Boot Priority Order" → Network, HDD, all other sources disabled


Fujitsu Stylistic R726
~~~~~~~~~~~~~~~~~~~~~~

Infos
"""""

* WOL does not seem to work although NIC link is up in S5.

System firmware setup
"""""""""""""""""""""

* Enter setup via F2
* "Security" → "Secure Boot Configuration" → "Secure Boot Option" → "Disabled"
  Needed to enable CSM.
* "Security" → "Set Supervisor Password" → set password
* "Security" → "Boot from Removable Media" → "Supervisor Only"
* "Security" → "Boot Menu" → "Disabled"
  (In UEFI mode, the Opsi boot image did not boot).
* "Advanced" → "CSM" → "Enabled"
  Needed to allow PXE boot of the Opsi boot image.
* "Advanced" → "Internal Device Configuration" → "Internal Cameras" → "Disabled"
* "Advanced" → "Wake up on LAN" → "Enabled"
* "Advanced" → "Intel(R) VT-d" → "Enabled"
* "Boot" → "Boot Priority Order" → Network, SSD, all other sources disabled
