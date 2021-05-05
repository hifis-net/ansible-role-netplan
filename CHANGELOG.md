<!--
SPDX-FileCopyrightText: 2021 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2021 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Group your changes into these categories:

`Added`, `Changed`, `Deprecated`, `Removed`, `Fixed`, `Security`.

## [0.3.1](https://gitlab.com/hifis/ansible/netplan-role/-/releases/v0.3.1) - 2021-05-05

[List of commits](https://gitlab.com/hifis/ansible/netplan-role/-/compare/v0.3.0...v0.3.1)

### Fixed

- Add checks to determine whether reboot of hosts are necessary when switching to Netplan
  ([!15](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/15)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).

## [0.3.0](https://gitlab.com/hifis/ansible/netplan-role/-/releases/v0.3.0) - 2021-03-17

[List of commits](https://gitlab.com/hifis/ansible/netplan-role/-/compare/v0.2.1...v0.3.0)

### Added

- Backup configuration file when changing the Netplan network configuration
  ([!8](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/8)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).
- Add a section to file README to inform users about networking limitations of the role
  ([!10](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/10)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).
  
### Changed

- Use templating comments for copyright notice in template config.yaml.j2
  ([!7](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/7)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).

### Fixed

- Reboot managed node if migrating networking from ifupdown to netplan
  ([!13](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/13)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).

## [0.2.1](https://gitlab.com/hifis/ansible/netplan-role/-/releases/v0.2.1) - 2021-03-10

[List of commits](https://gitlab.com/hifis/ansible/netplan-role/-/compare/v0.2.0...v0.2.1)

### Fixed

- Remove task that uninstalls package 'ifupdown' from role tasks
  ([!6](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/6)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).

## [0.2.0](https://gitlab.com/hifis/ansible/netplan-role/-/releases/v0.2.0) - 2021-03-01

[List of commits](https://gitlab.com/hifis/ansible/netplan-role/-/compare/v0.1.0...v0.2.0)

### Added

- Add a task that removes the package 'ifupdown' in favour of 'netplan'
  ([!2](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/2)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).

### Changed

- Refine the Netplan configuration file template
  ([!3](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/3)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).

### Changed

- Call handler to gather facts after IP addresses have been changed by Netplan
  ([!4](https://gitlab.com/hifis/ansible/netplan-role/-/merge_requests/4)
  by [christian.hueser.hzdr](https://gitlab.com/christian.hueser.hzdr)).

## [0.1.0](https://gitlab.com/hifis/ansible/netplan-role/-/releases/v0.1.0) - 2021-01-25

### Added

Initial release of the Ansible Netplan Role.
