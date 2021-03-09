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

## Unreleased

[List of commits](https://gitlab.com/hifis/ansible/netplan-role/-/compare/v0.2.0...main)

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
