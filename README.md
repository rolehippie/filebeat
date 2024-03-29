# filebeat

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/filebeat)
[![General Workflow](https://github.com/rolehippie/filebeat/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/filebeat/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/filebeat/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/filebeat/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/filebeat/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/filebeat/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/filebeat)](https://github.com/rolehippie/filebeat/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.filebeat-blue)](https://galaxy.ansible.com/rolehippie/filebeat)

Ansible role to install and configure filebeat.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [filebeat_console_enabled](#filebeat_console_enabled)
  - [filebeat_default_inputs](#filebeat_default_inputs)
  - [filebeat_default_modules](#filebeat_default_modules)
  - [filebeat_default_processors](#filebeat_default_processors)
  - [filebeat_group_inputs](#filebeat_group_inputs)
  - [filebeat_group_modules](#filebeat_group_modules)
  - [filebeat_group_processors](#filebeat_group_processors)
  - [filebeat_host_inputs](#filebeat_host_inputs)
  - [filebeat_host_modules](#filebeat_host_modules)
  - [filebeat_host_processors](#filebeat_host_processors)
  - [filebeat_keyring](#filebeat_keyring)
  - [filebeat_logging_level](#filebeat_logging_level)
  - [filebeat_logging_selectors](#filebeat_logging_selectors)
  - [filebeat_logging_to_files](#filebeat_logging_to_files)
  - [filebeat_logstash_enabled](#filebeat_logstash_enabled)
  - [filebeat_logstash_hosts](#filebeat_logstash_hosts)
  - [filebeat_major_version](#filebeat_major_version)
  - [filebeat_name](#filebeat_name)
  - [filebeat_service_enabled](#filebeat_service_enabled)
  - [filebeat_tags](#filebeat_tags)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### filebeat_console_enabled

#### Default value

```YAML
filebeat_console_enabled: false
```

### filebeat_default_inputs

List of default inputs, gets directly transformed to yaml

#### Default value

```YAML
filebeat_default_inputs:
  - type: log
    enabled: true
    paths:
      - /var/log/kern.log
    fields:
      kern: true
  - type: log
    enabled: true
    paths:
      - /var/log/dpkg.log
    fields:
      dpkg: true
```

#### Example usage

```YAML
filebeat_default_inputs:
  - type: log
    enabled: True
    paths:
      - /var/log/*.log
```

### filebeat_default_modules

List of default modules, gets directly transformed to yaml

#### Default value

```YAML
filebeat_default_modules:
  - module: system
    syslog:
      enabled: false
    auth:
      enabled: true
```

### filebeat_default_processors

List of default processors, gets directly transformed to yaml

#### Default value

```YAML
filebeat_default_processors:
  - add_host_metadata:
  - add_cloud_metadata:
  - add_docker_metadata:
```

### filebeat_group_inputs

List of group inputs, merged with filebeat_default_inputs

#### Default value

```YAML
filebeat_group_inputs: []
```

### filebeat_group_modules

List of group modules, merged with filebeat_default_modules

#### Default value

```YAML
filebeat_group_modules: []
```

### filebeat_group_processors

List of group processors, merged with filebeat_default_processors

#### Default value

```YAML
filebeat_group_processors: []
```

### filebeat_host_inputs

List of host inputs, merged with filebeat_default_inputs

#### Default value

```YAML
filebeat_host_inputs: []
```

### filebeat_host_modules

List of host modules, merged with filebeat_default_modules

#### Default value

```YAML
filebeat_host_modules: []
```

### filebeat_host_processors

List of host processors, merged with filebeat_default_processors

#### Default value

```YAML
filebeat_host_processors: []
```

### filebeat_keyring

Path for the repository keyring

#### Default value

```YAML
filebeat_keyring: /usr/share/keyrings/elastic-archive-keyring.gpg
```

### filebeat_logging_level

Define logging level

#### Default value

```YAML
filebeat_logging_level: warning
```

### filebeat_logging_selectors

Define logging selectors, like beat, publish, service

#### Default value

```YAML
filebeat_logging_selectors: []
```

### filebeat_logging_to_files

Log to files, keep journal clean

#### Default value

```YAML
filebeat_logging_to_files: true
```

### filebeat_logstash_enabled

#### Default value

```YAML
filebeat_logstash_enabled: true
```

### filebeat_logstash_hosts

#### Default value

```YAML
filebeat_logstash_hosts: []
```

### filebeat_major_version

Major version to install, used for the APT repository

#### Default value

```YAML
filebeat_major_version: 7
```

### filebeat_name

Name of the shipper within the output

#### Default value

```YAML
filebeat_name: '{{ ansible_hostname }}'
```

### filebeat_service_enabled

Enable the console output

### filebeat_tags

List of tags to assign for the shipper

#### Default value

```YAML
filebeat_tags: []
```

## Discovered Tags

**_filebeat_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
