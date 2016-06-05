Getting started
===============

.. contents::
   :local:

.. include:: includes/all.rst


Example inventory
-----------------

Add the hosts on which Opsi should be manage to the
``ypid_service_opsi`` Ansible inventory host group:

.. code:: ini

    [ypid_service_opsi]
    hostname

Example playbook
----------------

Here's an example playbook that can be used to setup and manage X2go server:

.. literalinclude:: playbooks/opsi.yml
   :language: yaml

This playbooks is shipped with this role under :file:`docs/playbooks/opsi.yml`
from which you can symlink it to your playbook directory.

Ansible tags
------------

You can use Ansible ``--tags`` or ``--skip-tags`` parameters to limit what
tasks are performed during Ansible run. This can be used after host is first
configured to speed up playbook execution, when you are sure that most of the
configuration has not been changed.

Available role tags:

``role::opsi``
  Main role tag, should be used in the playbook to execute all of the role
  tasks as well as role dependencies.

``role::opsi:pkg_install``
  Tasks related to the installation of additional system packages.

``role::opsi:prod_update``
  Tasks related to OPSI product updating.

``role::opsi:installfiles``
  Tasks related to OPSI product installation files.