ansible-logstash role
=====================

This role installs logstash.

Variables
----------

- `logstash_plugins`: plugin list to install (default: [])

Tests
-----

Test can then be run using vagrant:

```
vagrant up
vagrant ssh -c specs
```

Licence
-------

MIT

Authors
-------
@leucos - Michel Blanc
