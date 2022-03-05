# ruuvicollector-ansible

Ansible role to install and configure https://github.com/Scrin/RuuviCollector

## Created for personal use and tested with 

* RaspberryPi OS Lite (32-bit)
* RaspberryPi ZeroW 2

## Role Variables

### Mandatory

None

### Optional

* `ruuvicollector_version` (string, default "v0.2.7")
* `ruuvicollector_release_filename` (string, default "ruuvi-collector-0.2.jar")
* `ruuvicollector_influx_instance` (string, default http://localhost:8086")
* `ruuvicollector_influx_database` (string, default "ruuvi")
* `ruuvicollector_influx_measurement` (string, default "ruuvi_measurements")
* `ruuvicollector_influx_username` (string, default "ruuvi")
* `ruuvicollector_influx_retentionpolicy` (string, default "autogen")
* `ruuvicollector_influx_batch_mode` (boolean, default true)
* `ruuvicollector_measurement_interval` (int, default 9900)
* `ruuvicollector_measurement_strategy` (string, default "default")
* `ruuvicollector_ruuvi_names` (list, default null)

## Example usage

ansible.cfg
```
[defaults]
roles_path = roles
```

requirements.yml
```
- src: https://github.com/hulkk/ruuvicollector-ansible
```

`ansible-galaxy install -r requirements.yml --force`

site.yml
```
- hosts: ruuvi
  roles:
     - ruuvicollector-ansible
```

