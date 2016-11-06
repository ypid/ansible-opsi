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

This playbook is shipped with this role under :file:`docs/playbooks/opsi.yml`
from which you can symlink it to your playbook directory.
In case you use multiple roles maintained by ypid_, consider
using `ypid-ansible-common`_.

Ansible tags
------------

You can use Ansible ``--tags`` or ``--skip-tags`` parameters to limit what
tasks are performed during Ansible run. This can be used after a host was first
configured to speed up playbook execution, when you are sure that most of the
configuration is already in the desired state.

Available role tags:

``role::opsi``
  Main role tag, should be used in the playbook to execute all of the role
  tasks as well as role dependencies.

``role::opsi:pkgs``
  Tasks related to system package management like installing, upgrading or
  removing packages.

``role::opsi:prod_update``
  Tasks related to OPSI product updating.

``role::opsi:installfiles``
  Tasks related to OPSI product installation files.
