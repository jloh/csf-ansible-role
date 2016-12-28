CSF Ansible Role
=========

[![GitHub version](https://badge.fury.io/gh/jloh%2Fcsf-ansible-role.svg)](http://badge.fury.io/gh/jloh%2Fcsf-ansible-role) [![Build Status](https://travis-ci.org/jloh/csf-ansible-role.svg?branch=master)](https://travis-ci.org/jloh/csf-ansible-role)

Requirements
------------

None

Role Variables
--------------

Variables are done in two stages:

 * `csf_global_conf`  
   Variables within this scope are done at a group level and are deployed to all servers
 * `csf_conf`  
   Variables within this scope should only be done on a per-server basis
 * `csf_allow_ip`
   Values in that array will be added to /etc/csf/csf.allow file 
 * `csf_rules`  
   Rules placed into this variable are copied from [`role_dir/files/rules/common/{{ item.rule }}.allow`](files/rules/common)  
   **TODO:** Make this a lot neater

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: firewalls
  roles:
     - { role: jloh.csf-ansible-role }
```

In `group_vars/firewalls`:

```yaml
csf_global_conf:
  - name: CLUSTER_PORT
    config: "7786"
  - name: CLUSTER_KEY
    config: "some random cluster key"
  - name: DENY_TEMP_IP_LIMIT
    config: "200"
  - name: LF_CONSOLE_EMAIL_ALERT
    config: "1"
  - name: LF_GLOBAL
    config: "3600"
  - name: GLOBAL_DYNDNS_INTERVAL
    config: "600"
  - name: URLGET
    config: "2"

csf_allow:
 - 12.12.12.12	# office IP
 - 138.44.33.22	# monitoring
 - 198.33.22.11
 - 45.22.11.22
 
csf_ignore:
 - 12.12.12.12	# office IP
 - 138.44.33.22	# monitoring
 - 198.33.22.11
 - 45.22.11.22

csf_blocklists:
  - SPAMEDROP
  - DSHIELD
  - TOR
  - ALTTOR
  - BOGON
  - HONEYPOT
  - CIARMY
  - BFB
  - OPENBL
  - AUTOSHUN
  - MAXMIND
  - BDE
  - STOPFORUMSPAM
```


In `host_vars/firewall-01`:

```yaml
csf_conf:
  - name: CLUSTER_RECVFROM
    config: "162.243.144.14,103.4.18.200,80.69.77.247"
  - name: CLUSTER_SENDTO
    config: "162.243.144.14,103.4.18.200,80.69.77.247"
  - name: TCP_IN
    config: "80,443"
  - name: TCP_OUT
    config: "25,53,80,443"
  - name: UDP_IN
    config: ""
  - name: UDP_OUT
    config: "25,123"
  - name: TCP6_IN
    config: "80,443"
  - name: TCP6_OUT
    config: "25,53,80,443"
  - name: UDP6_IN
    config: ""
  - name: UDP6_OUT
    config: "25,123"

 csf_rules:
  - rule: nagios
  - rule: munin
```

License
-------

MIT

Contributors
------------

Many! Please checkout [the contributors graph!](https://github.com/jloh/csf-ansible-role/graphs/contributors)

Author Information
------------------

For other roles and general tech information please feel free to checkout [my blog](https://jloh.co/l/blog/#pk_campaign=GitHub-Project&pk_kwd=csf-ansible-role).
