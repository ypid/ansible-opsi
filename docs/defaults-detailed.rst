.. _opsi__ref_default_variable_details:

Default variable details
========================

.. include:: includes/all.rst

Some of ``ypid.opsi`` default variables have more extensive
configuration than simple strings or lists, here you can find documentation and
examples for them.

.. contents::
   :local:
   :depth: 1


.. _opsi__ref_products:

Install and remove Opsi products
--------------------------------

``src_opsi_file``
  Optional, string. File path to the Opsi product file on the Ansible controller.

``state``
  Optional, string. State of the Opsi product.
  Defaults to ``present``.

  Choices:

  ``present``
    Opsi product will be installed if needed.

  ``copied``
    Opsi product file(s) will be copied to the Opsi server. The installation
    state of the product will not be altertet.

  ``absent``.
    Opsi product will be removed if needed.


.. _opsi__ref_installfiles:

OPSI product installation files
-------------------------------

.. _opsi__ref_controller_archive_file_path:

``controller_archive_file_path``
  Required, string. File path to the archive file on the Ansible controller to use
  as the OPSI product‘s installation files.

.. _opsi__ref_archive_checksum:

``archive_checksum``
  Optional, dict. The key is the hashing algorithm, the value is the expected
  checksum value of the archive file.

  Example::

    archive_checksum:
      sha1: 'da39a3ee5e6b4b0d3255bfef95601890afd80709'

  Refer to :any:`opsi__installfiles_achrive_hash_algo_preference` for more
  details.
