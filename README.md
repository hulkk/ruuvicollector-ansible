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
* `ruuvicollector_influx_password` (string, default null)
* `ruuvicollector_influx_retentionpolicy` (string, default "autogen")
* `ruuvicollector_influx_batch_mode` (boolean, default true)
* `ruuvicollector_measurement_interval` (int, default 9900)
    * minimum interval in milliseconds for measurements per measurement type per tag
* `ruuvicollector_ruuvi_names` (list, default null)
    * maps ruuvitag mac addresses to human readable names
    * e.g. `D944923E0B70=Terrace`
* `ruuvicollector_measurement_list` (list, default null)
    * list of measurement field names to collect, by default all measurements are collected
    * https://github.com/Scrin/RuuviCollector/blob/master/MEASUREMENTS.md

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

