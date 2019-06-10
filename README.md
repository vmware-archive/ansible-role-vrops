# ansible-role-vrops

Ansible playbook to automate installing, upgrading and configuring vROps.

## Requirements

This role currently supports Debian/Ubuntu distros and requires a valid installation of VMware's OVFTools.

## Role Variables

```yaml
# Where the the ovftool is located by default
vrops_ovftool: /usr/local/bin/ovftool/ovftool

# Where the OVA file for the vROps installation exists.
vrops_ova_location: "/var/www/html/downloads"

# Whether to enable SSH access on the installed appliance(s).
vrops_enable_ssh: true

# The provisioning mode for the disk on installation.
vrops_disk_mode: 'thin'

# The IP protocol version to support.
vrops_ip_protocol: 'IPv4'

# Where to place generated password (http) body files during play runs.
adminpass_body_file: '/tmp/adminpass-body.json'

# Where to place generated body role files during play runs.
role_body_prefix: '/tmp/role-body'

# Where to place generated cluster body files during play runs.
cluster_name_body_file: '/tmp/cluster-name-body.json'

# Where to place generated slice name (HTTP) body files during play runs.
slice_name_body_file: '/tmp/slice-name-body.json'

# Where to place generated cluster state (HTTP) body files during play runs.
cluster_state_body_file: '/tmp/init-cluster-body.json'

# The default administrator user to setup during deployment.
default_admin_user: 'admin'
```

## Example playbook

```
---
- name:  Deploy OVA and create config.json for vio
  hosts: local
  roles:
    - vrops
  vars_files:
    - /vars/uianswers.yml
```

# License and Copyright
 
Copyright 2015 VMware, Inc.  All rights reserved.

SPDX-License-Identifier: Apache-2.0 OR GPL-3.0-only

This code is Dual Licensed Apache-2.0 or GPLv3

## Author Information

This role was created in 2015 by [Anne Ebie / VMware](http://www.vmware.com/).
