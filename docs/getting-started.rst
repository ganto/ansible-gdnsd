Getting started
===============

.. contents::
   :local:

If you run the role without any user-defined variables it will simply install
the :program:`gdnsd` package and enable and start the service. No specific
service configuration or DNS zone data will be generated.


.. _gdnsd_example_inventory:

Example inventory
-----------------

The ``ganto.gdnsd`` role could be included in your Ansible setup by assigning
the DNS host(s) to a custom inventory group such as ``gdnsd_service``. E.g.::

    [gdnsd_service]
    hostname

The role can be run against multiple hosts (e.g. primary and secondary DNS
servers) and it will manage the DNS zone serial to be identical for the same
zone data on multiple hosts as long as the zone files are not manually adjusted
and zone updates are run concurrently against all servers.


.. _gdnsd_example_playbook:

Example playbook
----------------

Here's a minimal example Ansible playbook that uses the ``ganto.gdnsd`` role:

.. literalinclude:: playbooks/gdnsd.yml
   :language: yaml


.. _gdnsd_dns_zone_config:

DNS zone configuration
----------------------

If at least a single domain name is listed in :envvar:`gdnsd__zones` the role
will create a forward and reverse zone defining the host as primary name server
and adds a ``A`` and ``PTR`` record for the host to the zone files.

.. code-block:: yaml

    gdnsd__zones:
      - domain: example.com

This configuration can be further customized by defining the individual DNS
records in the ``records`` property of the zone item in :envvar:`gdnsd__zones`.
