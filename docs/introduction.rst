Introduction
============

`gdnsd <https://gdnsd.org/>`_ is a powerful Authoritative-only DNS server with
some advanced features such as geographic (or other sorts of) balancing,
redirection, wighting and service-state-conscious failover at the DNS layer.

`ganto.gdnsd <https://galaxy.ansible.com/ganto/gdnsd>`_ is an `Ansible
<https://www.ansible.com>`_ role to install and manage the :program:`gdnsd`
name service and is able to generate `RFC1035
<https://tools.ietf.org/html/rfc1035>`_ conformant zone files from domain name
records defined in the Ansible inventory. It will properly increase the serial
on zone updates.


.. _gdnsd_requirements:

Requirements
~~~~~~~~~~~~

This Ansible role can currently only be used on Debian- and Ubuntu-based
distribution that have the `gdnsd package <https://tracker.debian.org/pkg/gdnsd>`_
available in their repositories.

To run the role at least Ansible ``v2.7.0`` is required.


.. _gdnsd_installation:

Installation
~~~~~~~~~~~~

On the machine where Ansible is run the role can be installed by running:

.. code-block:: console

   ansible-galaxy install ganto.gdnsd

..
 Local Variables:
 mode: rst
 ispell-local-dictionary: "american"
 End:
