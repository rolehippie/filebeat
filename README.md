# filebeat

[![Build Status](https://cloud.drone.io/api/badges/rolehippie/filebeat/status.svg)](https://cloud.drone.io/rolehippie/filebeat)

Ansible role to configure filebeat

## Table of content

* [Default Variables](#default-variables)
  * [filebeat_service_enabled](#filebeat_service_enabled)
  * [filebeat_service_state](#filebeat_service_state)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### filebeat_service_enabled

Switch the service into enabled state

#### Default value

```YAML
filebeat_service_enabled: false
```

### filebeat_service_state

State for the service definition

#### Default value

```YAML
filebeat_service_state: stopped
```

## Dependencies

None.

## License

Apache-2.0

## Author

Thomas Boerger
