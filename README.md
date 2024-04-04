# ansible-role-server

Ansible role for setting up basic packages on an Ansible-managed server

## Requirements

This role depends on the following collections:
- `devsec.hardening` (tested with version 9.0.1)
- `prometheus.prometheus` (tested with version 0.15.1)

At the time of this writing, it is not possible for a stand-alone Ansible role to declare a dependency on a collection,
so you need to do this yourself. For example, in your playbook directory, you could have a `requirements.yml` file that
contains the following section.

```
collections:
  - name: devsec.hardening
    version: 9.0.1
  - name: prometheus.prometheus
    version: 0.15.1
```

Perhaps you should also add this role to the `roles` section of this file. Then you can install or upgrade your
dependencies with `ansible-galaxy install -r requirements.yml --force-with-deps`.

## Variables

- `server_node_exporter_port` [required]
- `server_node_exporter_prometheus_host_ip` [required]
- `server_pg_exporter_port` [required]
- `server_ssh_port` [default: `ssh` (alias for 22)]
