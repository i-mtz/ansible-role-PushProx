# Ansible Role: PushProx

## Description

Deploy prometheus [PushProx](https://github.com/prometheus-community/PushProx) using ansible.

## Requirements

- fqdn python library is required for the preflight (`pip install fqdn`)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml)

The default is to deploy the `pushprox-client` service, and only if variable `pushprox_proxy_mode` is set 
to `true` to deploy the `pushprox-proxy` service.


### Mandatory variables

For the _client_ service:
pushprox_client_fqdn: '' # this is needed and is validated against a fqdn

For the _proxy_ service `pushprox_proxy_mode` should be `true` and then a valid address set:
`pushprox_proxy_listen_address: ''`



## Example

### Playbook
Include the role
```yaml
- name: Configure pushprox
  ansible.builtin.import_role:
    name: pushprox
  tags:
    - pushprox
```

## License

This role was created using the [pushgateway](https://github.com/prometheus-community/ansible/tree/main/roles/pushgateway) role from the [prometheus-community](https://github.com/prometheus-community/ansible) ansible collection.

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
