# Another Apache2 ansible role

## Installation

* Put these lines in your `requirements.yml` file:   
  ```
  - src: https://github.com/sebbrochet/ansible-role-apache2
    version: master
    name: apache2
  ```
   
* Get the code with ansible-galaxy   
  `ansible-galaxy -r requirements.yml`

## Example Playbook
```
- hosts: servers
  roles:
    - { role: apache2, apache_https: True }
```
