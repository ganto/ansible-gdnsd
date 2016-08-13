Getting started
===============

.. contents::
   :local:

Example inventory
-----------------

The ``ganto.gdnsd`` role can be included in your Ansible setup by assigning
the DNS host(s) to a custom inventory group such as ``gdnsd_service``. E.g.::

    [gdnsd_service]
    hostname

Example playbook
----------------

Here's a minimal example Ansible playbook that uses the ``ganto.gdnsd`` role:

.. literalinclude:: playbooks/gdnsd.yml
   :language: yaml
