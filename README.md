Windows Exporter
=========
[![Role Name](https://img.shields.io/ansible/role/61839?label=Role%20Name&logo=ansible&style=flat-square)](https://galaxy.ansible.com/iquzart/windows_exporter)
[![Quality Score](https://img.shields.io/ansible/quality/61839?label=Quality%20Score&logo=ansible&style=flat-square)](https://galaxy.ansible.com/iquzart/windows_exporter)
[![Role Downloads](https://img.shields.io/ansible/role/d/61839?label=Role%20Downloads&logo=ansible&style=flat-square)](https://galaxy.ansible.com/iquzart/windows_exporter)
[![License](https://img.shields.io/:license-mit-blue.svg?style=flat-square)](https://badges.mit-license.org)


Ansible role for Windows Exporter setup.


Features
--------------
  ```
  1. Download and install Windows Exporter.
  2. Configure Windows Exporter with config.yaml file.
  3. Enable Collectors based on service availability in the target system (IIS, MSSQL, ADDC, ADCS, MSMQ).
  4. Upgrade or Downgrade the windows exporter version.
  5. Configurable service Listen address and Port.
  6. Configure windows Firewall.
  ```


Role Variables
--------------

| Variable | Description | Default | 
| --- | --- | --- |
| windows_exporter_common_collectors | common collectors to enable | cpu, cs, logical_disk, memory, net, os, process, service, system, tcp, textfile | 
| windows_exporter_version | WIndows Exporter Version to be installed | 0.19.0 |
| windows_exporter_download_url | Windows Exporter MSI URL | https://github.com/prometheus-community/windows_exporter/releases |
| windows_exporter_service_name | Windows Exporter Service name | windows_exporter |
| windows_exporter_listen_address | Windows Exporter Service listen address | 0.0.0.0 |
| windows_exporter_port | Windows Exporter port | 9182 |
| windows_exporter_install_path | Windows Exporter install path | C:\Program Files\windows_exporter |
| windows_exporter_textfile_collector_directory | Windows Exporter Text file collector directory | C:\Program Files\windows_exporter\textfile_inputs |
| windows_exporter_download_path | MSI Download path | C:\Install\exporters |
| windows_exporter_log_level | Log Level | debug |
| windows_exporter_start_mode | Windows Exporter Service start mode | delayed |
| windows_exporter_configure_firewall | Configure firewall for windows exporter | true |


Example Playbook
----------------
```
    - hosts: servers
      roles:
        - iquzart.windows_exporter
```

License
-------

MIT


Author Information
------------------

Muhammed Iqbal <iquzart@hotmail.com>