Introduction
============

.. include:: includes/all.rst


The ``ypid.opsi`` role is meant for managing the software distribution and
management system Opsi_ (open PC server integration). Opsi_ primarily targets
`Microsoft Windows`_ clients but can also install and manage GNU_/Linux_ hosts.

While this role is designed to be flexible enough to be used with a variety of
different Opsi server deployments, the original authors primary use case of
this role was to automate `paedML Linux`_ school environment deployment and
support. In case you have the same intention, chances are you might be
interested in the ypid.paedml_linux_ role.

Because of this, the role currently does not supports setting up the Opsi_
server because this is already done when deploying the `paedML Linux`_ VM
templates.

The main focus of the role is to do the finishing touches on the Opsi_ server
like installing additional Opsi_ products and completing Opsi_ products
containing proprietary software, which can not be shipped in a ready to use
form.


Installation
~~~~~~~~~~~~

This role requires at least Ansible ``v2.1.3``. To install it, run::

    ansible-galaxy install ypid.opsi

..
 Local Variables:
 mode: rst
 ispell-local-dictionary: "american"
 End:
