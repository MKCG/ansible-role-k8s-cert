# ansible-role-k8s-cert
Generate p12 file from a k8s instance using openssl

## Variables

| Name               | Default value  | Description                                                |
|--------------------|----------------|------------------------------------------------------------|
| kube_config_path   | ~/.kube/config | Kubernetes configuration filepath                          |
| kube_cert_dir      | /opt/kube-cert | Path where the p12 file will be created                    |
| kube_cert_password | kevin-masseix  | Password used to generate the p12 file. You MUST change it |

## Playbook example

```yml
---
- name: Install Kubernetes master nodes
  hosts: kube_master_node

  vars:
    kube_cert_password: azertyuiop

  tasks:
    - name: Configure docker
      include_role:
        name: ansible-role-k8s-cert

```
