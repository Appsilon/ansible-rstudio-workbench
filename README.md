# Ansible Role: rstudio-workbench

[![CI](https://github.com/Appsilon/ansible-rstudio-workbench/workflows/CI/badge.svg)](https://github.com/Appsilon/ansible-rstudio-workbench/actions/workflows/ci.yml)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-appsilon.rstudio_workbench-blue.svg)](https://galaxy.ansible.com/appsilon/rstudio_workbench/)

Set up (the latest version of) [RStudio Workbench](https://www.rstudio.com/products/workbench/) in Debian-like systems.

## Requirements

* `curl` (will be installed)
* `r-base` (will not be installed)

## Role Variables

* `rstudio_workbench_version` [default: `2021.09.0-351.pro6`]: Version to install
* `rstudio_workbench_install` [default: `[]`]: Additional packages to install (e.g. `r-base`)
* `rstudio_workbench_www_port` [default: `8787`]: The port you want RStudio Workbench to listen on
* `rstudio_workbench_config_override` [default: `""`]: If you know what you're doing, you can override or add to any of `rserver.conf` config options.
* `rstudio_workbench_license`: If specified, RStudio Workbench will attempt to activate the supplied license key.

For the rest of the default variables, see
[./defaults/main.yml](./defaults/main.yml).

## Dependencies

None

## Example

```yaml
---
- hosts: all
  roles:
    - rstudio-workbench
```

## License

MIT

## Author Information

Damian Budelewski. Inspired by [ansible-rstudio-server](https://github.com/Oefenweb/ansible-rstudio-server).
