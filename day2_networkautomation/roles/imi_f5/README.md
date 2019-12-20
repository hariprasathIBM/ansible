Role Name
=========

Role for F5 cli commands based on IMI Usecases.

Requirements
------------

- Connectivity to BRNO Lab environment
  - Booking/Reservation should be done upfront for F5 Lab
  - Use IBM intranet id to authenticate to Firewall, Lab access
  - Use a socks5 proxy client to connect to Jump Host

- BRNO Lab main page: https://w3-connections.ibm.com/wikis/home?lang=en-us#!/wiki/W2221d71e4053_4442_8e8d_392188a4816c/page/Network
  - BSO Firewall Authentication URL: https://9.138.240.167/netaccess/loginuser.html
  - Booking system URL: http://moon.brno-centrum.cz.ibm.com/

- Proxy Client Authentication:
  - User: IBM Intranet Id (without @xx.ibm.com)
  - Password: placeholderpassword

- F5 Lab Machine details URL: https://w3-connections.ibm.com/wikis/home?lang=en-us#!/wiki/W2221d71e4053_4442_8e8d_392188a4816c/page/F5%20Lab

Role Variables
--------------

- defaults/main.yml

```
f5_provider:
  server: "{{inventory_hostname}}"
  user: "{{ansible_user}}"
  password: "{{ansible_password}}"
  transport: cli
  timeout: 600
  validate_certs: False
```

Dependencies
------------

- None

Example Playbook
----------------

To retrieve F5 Failover Status

    - hosts: servers
      roles:
         - { role: imi_f5, }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
