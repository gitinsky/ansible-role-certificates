ansible-role-certificates
=========================

tested on ubuntu 12.04

```
dependencies:
    - { role: certificates, ssl_name: "{{ rd_ssl_name }}"}
```

You can also set ```ssl_trust_local_ca``` to ```true``` to make host trust itself.

If you are using startssl, you can take csr, replace crt and add chain certificates to it with the following command:

```
curl http://www.startssl.com/certs/sub.class1.server.ca.pem | tee -a /etc/pki/tls/certs/yourdomain.com.crt
curl http://www.startssl.com/certs/ca.pem                   | tee -a /etc/pki/tls/certs/yourdomain.com.crt

```

### Local certificate generation

Hosts:

```yml
localhost  ansible_connection=local
```

playbook:

```yml
- hosts: localhost
  roles:
    - { role: certificates, ssl_cert_root: ./, ssl_name: me.not }
```
