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

``auto_reverse_zone``
  Optional. Automatically generate reverse zone for this domain. Default to
  :envvar:`gdnsd__auto_reverse_zone`. Individual records can be excluded from
  the reverse zone by setting ``do_reverse: False`` in the record item
  definition.

``reverse_zone``
  Name of the reverse zone (e.g. '1.168.192.in-addr.arpa'). Required if this
  is a reverse zone. Optional if this is a forward zone that has
  ``auto_reverse_zone`` enabled. In this case it defaults to
  :envvar:`gdnsd__default_reverse_zone`.

``primary_nameserver``
  Optional. DNS name of the primary name server for this zone which is added
  to the zone's SOA record. Must be a FQDN. Defaults to the host name where
  :program:`gdnsd` is installed.

``mailbox``
  Optional. Mail address of the person in charge of the zone. Defaults to
  ``hostmaster@{{ item.domain }}``.

``refresh``
  Optional. Time interval before the zone should be refreshed. Defaults to
  :envvar:`gdnsd__refresh`.

``retry``
  Optional. Time interval that should elapse before a failed refresh should
  be retried. Defaults to :envvar:`gdnsd__retry`.

``expire``
  Optional. Specifies how long zone data is considered valid in case the zone
  cannot be refreshed from the primary name server. Defaults to
  :envvar:`gdnsd__expire`.

``negative_cache``
  Optional. Negative caching TTL. Defaults to :envvar:`gdnsd__negative_cache`.

``nameservers``
  Optional. List of authoritative name servers for this zone. For each entry
  a NS record will be added to the zone file. By default only the host running
  :program:`gdnsd` will be set as authoritative name server.

``records``
  Optional. List of DNS records for this zone. Each records is defined as a
  YAML dictionary with the following properties:

  ``name``
    Required (except for ``item.type: MX``). Record name. Depending on the
    record type, this is e.g. a host name.

  ``type``
    Optional. Record type. Supported are ``A``, ``AAAA``, ``CNAME``, ``MX``,
    ``SRV`` and ``TXT``. Defaults to ``A`` record.

  ``do_reverse``
    Optional. If ``item.type`` is ``A``, add a reverse zone entry for this
    record. Defaults to ``True`` if ``auto_reverse_zone: True`` for this zone.

  ``target``
    Required. Resource data which is served when querying the record.
    Depending on the record type this is e.g. a host address.

  ``ttl``
    Optional. Individual record TTL.

  ``preference``
    Optional. Preference given to this record among others with the same data.
    Lower values are preferred. Only valid for ``MX`` and ``SRV`` record types.
    Defaults to ``5``.

  ``weight``
    Optional. A server selection mechanism. The weight field specifies a
    relative weight for entries with the same preference. Larger weights should
    be given a proportionately higher probability of being selected. Only
    valid for ``SRV`` record type. Defaults to ``0``.

  ``port``
    Required. The port on this target host of this service. Only valid for
    ``SRV`` record type.
