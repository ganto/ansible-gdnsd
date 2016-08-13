Introduction
============

`gdnsd <http://gdnsd.org/>`_ is a powerful Authoritative-only DNS server with
some advanced features such as geographic (or other sorts of) balancing,
redirection, wighting and service-state-conscious failover at the DNS layer.

The ``ganto.gdnsd`` Ansible role installs and configures the name service and
is able to generate zone files from name records defined in the Ansible
inventory.

Installation
~~~~~~~~~~~~

This role requires at least Ansible ``v1.9.0``. To install it run:

.. code-block:: console

   user@host:~$ git clone https://github.com/ganto/ansible-gdnsd ganto.gdnsd

..
 Local Variables:
 mode: rst
 ispell-local-dictionary: "american"
 End:
