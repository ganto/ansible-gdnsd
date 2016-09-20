Default variable details
========================

Some of ``ganto.gdnsd`` default variables have more extensive configuration
than simple strings or lists, here you can find documentation and examples
for them.

.. contents::
   :local:
   :depth: 1


.. _gdnsd__ref_zones:

gdnsd__zones
------------

This list is used to configure the DNS zones which are served by
:program:`gdnsd`. Each list element corresponds to zone entry which is a
YAML dictionary with the following parameters:

``domain``
  Domain name of the DNS zone. Required, if this is a forward zone.

``reverse_zone``
  Optional. Set this to ``True`` to mark zone entry as reverse zone. Defaults
  to ``False``.

``reverse_network``
  Network definition for reverse zone. Required, if this is a reverse zone.

``primary_nameserver``
  Optional. DNS name of the primary name server for this zone which is added
  to the zone's SOA record. Must be a FQDN. Defaults to the host name where
  :program:`gdnsd` is installed.

``mailbox``
  Optional. Mail address of the person in charge of the zone. Defaults to
  ``hostmaster@{{ item.domain }}``.

``refresh``
  Optional. Time interval before the zone should be refreshed. Defaults to
  :env:`gdnsd__refresh`.

``retry``
  Optional. Time interval that should elapse before a failed refresh should
  be retried. Defaults to :env:`gdnsd__retry`.

``expire``
  Optional. Specifies how long zone data is considered valid in case the zone
  cannot be refreshed from the primary name server. Defaults to
  :env:`gdnsd__expire`.

``negative_cache``
  Optional. Negative caching TTL. Defaults to :env:`gdnsd__negative_cache`.

``nameservers``
  Optional. List of authoritative name servers for this zone. For each entry
  a NS record will be added to the zone file. By default only the host running
  :program:`gdnsd` will be set as authoritative name server.

``records``
  Optional. List of DNS records for this zone. Each records is defined as a
  YAML dictionary with the following properties:

  ``name``
    Required. Record name. Depending on the record type, this is e.g. a
    host name.

  ``type``
    Optional. Record type. Defaults to ``A`` record.

  ``rdata``
    Required. Resource data which is served when querying the record.
    Depending on the record type this is e.g. a host address.

  ``do_reverse``
    Optional. If ``item.type`` is ``A``, add a reverse zone entry for this
    record.
