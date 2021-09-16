# Ansible role - chrony
This role setups chrony service, sets timezone and NTP synchronization.

[[_TOC_]]

## Description
This role supports Debian-based Linux systems. Any timezone from `tz database` should work properly, you can find the list on [Wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).
For NTP synchronization, you can use either a NTP pool (recommended) or an individual server.

## Requirements
* This role requires root access, so you either need to specify `become` directive as a global or while invoking the role.

    ```yml
    become: yes
    ```

## Parameters

Optional.

- `chrony_timezone` - timezone to be set. Default: `Etc/UTC`
- `chrony_ntp_server` - NTP server/pool to use for synchronization. Default: `1.debian.pool.ntp.org`

## Example

The simplest example of NTP timezone settings.

```yaml
roles:
  - role: chrony
    chrony_timezone: Europe/Prague
    chrony_ntp_server: pool.ntp.org
    become: yes
```

## License

Copyright (c) KYPO Team. All rights reserved.

Licensed under the [MIT](LICENSE) license.

## Acknowledgements

[KYPO Team](https://crp.kypo.muni.cz/)
