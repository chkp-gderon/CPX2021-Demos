# CPX 360 2021 - Security Policy as Code: A Beginners Guide

## Overview

This repository is a simplified version of the [AnsibleFest2020-Demos](https://github.com/CheckPointSW-Community/AnsibleFest2020-Demos) and contains the code as demonstrated at the CPX 360 2021 Breakout Session: Security Policy as Code, A Beginners Guide.

## What does it do?

The Ansible Playbook updates an existing security policy package on a Check Point Management server that is used as a shared Policy Layer. The intention is to create a security policy that is partly managed by a security administrator (parent rule) and partly managed as code (child rules).
The security policy is defined as variable file for Ansible in YAML format (orchestration_demo.yml). An ansible role is used as a collection of tasks to configure the policy objects and rules.

## Requirements

- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) - Version 2.9 or later
- [Ansible check_point.mgmt collection](https://galaxy.ansible.com/check_point/mgmt) - Included by default from version Ansible 2.9
  - **Note:** It is recommended to download the latest version from galaxy
- [Check Point Security Management and Gateway](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk160736) - Version R80.40 or later

## Usage

1. Clone the repository
2. Create a set_env_var.sh file with content like this (use your details):

```
export VAR_mgmt_api_user="Check Point Admin User"
export VAR_mgmt_api_password="Check Point Admin User"
export VAR_mgmt_api_key="Check Point Admin API Key"      
export VAR_mgmt_hostname="Check Secuity Management Hostname"
export VAR_mgmt_IP="Check Secuity Management IP"

``` 
3. From a command line, export your mgmt variables
> ```
> source ./set_env_var.sh
>```

4. From a command line, execute the playbook
> ```
> ansible-playbook Playbook.yml
> ```


## References
* [AnsibleFest2020-Demos](https://github.com/CheckPointSW-Community/AnsibleFest2020-Demos)
* [sk114661 - Automate your management server using "Ansible"](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk114661?tocpath=Posture%20Management%7CThe%20CloudGuard%20Dome9%20GSL%20Language%7C_____0)
* [Check Point Ansible collections](https://galaxy.ansible.com/check_point)
* [Check Point Ansible modules documentation](https://docs.ansible.com/ansible/2.9/modules/list_of_network_modules.html#check-point)
