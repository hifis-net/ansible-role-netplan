<!--
SPDX-FileCopyrightText: 2021 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2021 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

# Netplan Role

:warning: **This project is archived!** :warning:

This role has been migrated to our `hifis.toolkit` collection:

- <https://github.com/hifis-net/ansible-collection-toolkit>
- <https://galaxy.ansible.com/ui/repo/published/hifis/toolkit/>

[![CI Status](https://github.com/hifis-net/ansible-role-netplan/actions/workflows/ci.yml/badge.svg)](https://github.com/hifis-net/ansible-role-haproxy/actions/workflows/ci.yml)
[![Ansible Role: hifis.netplan](https://img.shields.io/badge/role-hifis.netplan-blue)](https://galaxy.ansible.com/ui/standalone/roles/hifis/netplan/)
[![Ansible Role Downloads](https://img.shields.io/ansible/role/d/hifis/netplan)](https://galaxy.ansible.com/ui/standalone/roles/hifis/netplan/)
[![Apache-2.0 Licensed](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/hifis-net/ansible-role-netplan/blob/main/LICENSES/Apache-2.0.txt)
[![Latest release](https://img.shields.io/github/v/release/hifis-net/ansible-role-netplan)](https://github.com/hifis-net/ansible-role-netplan/releases)

Ansible role to install and configure Netplan.

## Requirements

None.

## Role Variables

### Mandatory Variables to be Set that are Not Set with Defaults

#### Sample Network Configuration

Sample configuration to set up networking with Netplan:

```yaml
netplan_ethernets:
  - interface_name: 'eth0'
    dhcp4: 'no'
    routes:
      - to: 'default'
        via: '10.123.0.1'
    addresses:
      - '10.123.0.10/24'
    nameservers:
      addresses:
        - '8.8.8.8'
        - '9.9.9.9'
      search:
        - 'domain.local'
        - 'domain.name'
```

### Variables that are Set with Defaults

#### Flag to delete any pre-existing Netplan configuration files

Flag decides on whether pre-existing Netplan configuration files should be deleted:

```yaml
netplan_remove_existing_configs: true
```

#### Name of the Netplan Configuration File Template

Name of the template providing the Netplan configuration file:

```yaml
netplan_configuration_file_template: 'config.yaml.j2'
```

#### Directory of the Netplan Configuration Files

Directory of the Netplan configuration files:

```yaml
netplan_configuration_dir: '/etc/netplan'
```

#### Name of the Netplan Configuration File

Name of the Netplan configuration file:

```yaml
netplan_configuration_file: 'config.yaml'
```

#### Path to the Netplan Configuration File

Path to the Netplan configuration file:

```yaml
netplan_configuration_file_path: "{{ (netplan_configuration_dir, netplan_configuration_file) | path_join }}"
```

#### Packages to be Installed

List of packages that need to be installed:

```yaml
netplan_packages:
  - 'netplan.io'
```

#### Package ifupdown Network Configuration File

Network configuration file that is present if networking is managed by package ifupdown:

```yaml
ifupdown_ifstate_file: '/run/network/ifstate'
```

## Troubleshooting

### Cleaning Up: Please Uninstall Package ifupdown Manually

Before the package `ifupdown` can be safely removed netplan networking 
needs to be properly configured.
If the package is removed too early, the role will hang.

For that reason this role does **not** handle the removal of the `ifupdown` package.

## Limitations

### Bootstrapping Network Configurations is not Supported

Please note that networking configurations can not be bootstrapped during
role execution.
The respective managed nodes need networking to be configured beforehand.

### No support for changing the IP over which Ansible connects

Be aware that this role does not support changing the IP addresses
over which Ansible connects out of the box.
If you change the IP address over which Ansible connects,
you might end up in a hanging role as soon as `netplan apply`
is executed.
Ansible loses its SSH connection in that case.

## Dependencies

None.

## License

[Apache-2.0](LICENSES/Apache-2.0.txt)

## Author Information

[HIFIS Software Team](https://software.hifis.net)
