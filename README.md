<!--
SPDX-FileCopyrightText: 2021 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2021 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

# Netplan Role

Ansible role to install and configure Netplan.

## Requirements

None.

## Role Variables

### Name of the Netplan Configuration File

Name of the template providing the Netplan configuration file:

```yaml
netplan_configuration_file_template: 'config.yaml.j2'
```

### Path to the Netplan Configuration File

Path to the Netplan configuration file:

```yaml
netplan_configuration_file_path: '/etc/netplan/config.yaml'
```

### Packages to be Installed

List of packages that need to be installed alongside Netplan:

```yaml
netplan_packages:
  - 'netplan.io'
```

### Sample Network Configuration

Sample configuration to set up networking with Netplan:

```yaml
netplan_ethernets:
  - interface_name: 'eth0'
    dhcp4: 'no'
    gateway4: '10.1.0.1'
    addresses:
      - '10.1.0.10/24'
    nameservers:
      addresses:
        - '8.8.8.8'
        - '9.9.9.9'
```

## Dependencies

None.

## License

[Apache-2.0](LICENSES/Apache-2.0.txt)

## Author Information

[HIFIS Software Team](https://software.hifis.net)
