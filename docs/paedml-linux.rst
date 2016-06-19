paedML Linux 6.0
================

.. contents::
   :local:

.. include:: includes/all.rst


The main documentation on which this role builds on is:

* `Installationsanleitung-20160419.pdf`_ (language: German)

See `LMZ homepage for more documentation <https://www.lmz-bw.de/technische-unterstuetzung/kundenportal/linux/dokumentationen.html>`_ (language: German).

So if you are following this documentation more then once then you found the
right tool in this role because it can help you out in automating the
repetitive parts of this documentation away.

Refer to the `ypid.paedml_linux`_ which is the base Ansible role for setting up
`paedML Linux`_. The role also contains additional documentation regarding
`paedML Linux`_.

.. _opsi__ref_product_updater_paedml_linux:

Opsi product updates
--------------------

By default, product updates will be done using the ``-i`` option to install a
set of additional products which would not be installed otherwise.

   -i Install all downloadable packages from configured repositories (ignores excludes).

If you want to influence this behavior, checkout the
:envvar:`opsi__product_updater_options` variable.

As of 2016-06-01, ``-i`` causes the following products to be installed additionally:

* ``acroread``
* ``moviemaker``
* ``ms-encoder``
* ``mshotfix-vista-win2008-x64-glb``
* ``mshotfix-vista-win2008-x86-glb``
* ``mshotfix-win10-win2016-x64-glb``
* ``mshotfix-win10-x86-glb``
* ``mshotfix-win2003-winxp-x64-deu``
* ``mshotfix-win2003-x86-deu``
* ``mshotfix-win81-x86-glb``
* ``mshotfix-win8-win2012-x64-glb``
* ``mshotfix-win8-x86-glb``
* ``mshotfix-winxp-x86-deu``
* ``msservicepack``
* ``nfs``
* ``office_2003_hotfix``
* ``office-2013-servicepack-x86-deu``
* ``office_2016_hotfix``
* ``ooffice3``
* ``opsi-clonezilla``
* ``opsi-local-image-opensuse13-2``
* ``opsi-local-image-ubuntu``
* ``opsi-local-image-win10-x64``
* ``opsi-local-image-win8``
* ``opsi-local-image-win81``
* ``opsi-local-image-win8-x64``
* ``opsi-local-image-winxp``
* ``opsi-set-wim-imagenames``
* ``paedml-pcsperre``
* ``paedml-school-client``
* ``paint-net``

If you only need a few of those products, you can also consider to use something like::

   opsi__product_updater_options:
     - '-p'
     - 'paint-net,opsi-local-image-ubuntu'
