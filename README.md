# Ansible Role: rstudio-workbench

[![CI](https://github.com/Appsilon/ansible-rstudio-workbench/workflows/CI/badge.svg)](https://github.com/Appsilon/ansible-rstudio-workbench/actions/workflows/ci.yml)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-appsilon.rstudio_workbench-blue.svg)](https://galaxy.ansible.com/appsilon/rstudio_workbench/)

Set up (the latest version of) [RStudio Workbench](https://www.rstudio.com/products/workbench/) in Debian-like systems.

## Requirements

* `curl` (will be installed)
* `r-base` (will not be installed)

## Role Variables

* `rstudio_workbench_version` [default: `2022.12.0-353.pro20`]: Version to install.
* `rstudio_workbench_install` [default: `[]`]: Additional packages to install (e.g. `r-base`).
* `rstudio_workbench_www_port` [default: `8787`]: The port you want RStudio Workbench to listen on>
* `rstudio_workbench_health_check_enabled` [default: 0]: Decision if you want to activate `http://<server-address-and-port>/health-check` endpoint.
* `rstudio_workbench_rserver_config`: If specified (map), will add key=value records to `rserver.conf`.
* `rstudio_workbench_rsession_config`: If specified (map), will add key=value records to `rsession.conf`.
* `rstudio_workbench_database_config`: If specified (map), will add key=value records to `database.conf`.
* `rstudio_workbench_openid_config`: If specified (map), will add key=value records to `openid-client-secret`.
* `rstudio_workbench_secure_cookie_key`: If specified (value), will create `secure-cookie-key` file with content of this variable.
* `rstudio_workbench_env_vars`: If specified (map), will add key=value records to `openid-client-secret`.
* `rstudio_workbench_load_balancer_config`: If specified (map), will add key=value records to `load-balancer`.
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
