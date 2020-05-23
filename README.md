Keepalived
=========

This role sets keepalived, and creates an ingress-controller entity validation script.

Role Variables
--------------
You only need to add ip address to the variable file role/keepalived/defaults/main.yml

    ---
    vip_ipaddress: <vip_address>

You can also change the variable if necessary at the address role/master-node/defaults/main.yml

    ---
    ns_for_check: ingress-nginx # Specify the name namespace where the ingress-controller Default: ingress-nginx

Dependencies
------------

No dependency

Example Playbook
----------------

    - hosts: keepalived_node
      roles:
      - { role: common }

    - hosts: k8s_master[0]
      roles:
      - {role: master-node }

      - hosts: keepalived_node
      roles:
      - { role: keepalived }


Author Information
------------------

Vatolin Alexey
