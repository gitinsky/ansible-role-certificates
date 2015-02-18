ansible-role-certificates
=========================

tested on ubuntu 12.04

```
dependencies:
    - { role: certificates, ssl_name: "{{ rd_ssl_name }}"}
```

You can also set ```ssl_trust_local_ca``` to ```true``` to make host trust itself.