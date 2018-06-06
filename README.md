# Ansible Role: skydevops-java

[![License](https://img.shields.io/badge/License-Apache%202.0-brightgreen.svg)](https://opensource.org/licenses/Apache-2.0)

## Description

This role will install and configure Oracle Java 1.8.0_171/172 on RedHat/CentOS and Debian/Ubuntu systems. 

```Note: Need to manually switch the version. [In future release thsi will be just a change of variable]
```

## Requirements
- Ansible >=2.3
- EPEL Repo for RedHat/Centos, which can be installed automatically using the [common](https://github.com/5KYDEV0P5/common) ansible role.


## Role Variables
All the variable that can be overridden are stored in [vars/main.yml](vars/main.yml) or [defaults/main.yml](defaults/main.yml) file as shown in the table below:

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `java_version` | : 1.8.0_171 | Describes the version of Java that will be installed |
| `java_install_dir` | : /apps | The directory where the application is installed<br> Automatically created by [common](https://github.com/5KYDEV0P5/common) Role |
| `java_src_tar` | : jdk-8u171-linux-x64.zip | The name of the Oracle Java Archive |
| `java_home` | : /apps/jdk1.8.0_171 | JAVA_HOME ENV variable |
| `java_shared_home` | : /usr/shared/java | Symlink to the installed JAVA |
| `java_profile_sh` | : /etc/profile.d/jdk.sh | Jinja2 Template, which contains the info to source the ENV variables |



## Dependencies
- [common](https://github.com/5KYDEV0P5/common)

## Example

### Playbook Default file locations based on playbook execution 

```yaml
{# The defaults PATHS where Ansible looks for the files #}
When executing the playbook from the following path:
$ cd {{ path_on_server }}/
$ ansible-playbook {{playbook_dir}}/playbook.yml

   {{ path_on_server }}/roles/{{ ansible_role }}/files/jdk-8u171-linux-x64.zip   
   {{ path_on_server }}/roles/{{ ansible_role }}/jdk-8u171-linux-x64.zip   
   {{ path_on_server }}/roles/{{ ansible_role }}/tasks/files/jdk-8u171-linux-x64.zip   
   {{ path_on_server }}/roles/{{ ansible_role }}/tasks/jdk-8u171-linux-x64.zip   
   {{ path_on_server }}/{{ playbook_dir }}/files/jdk-8u171-linux-x64.zip   
   {{ path_on_server }}/{{ playbook_dir }}/jdk-8u171-linux-x64.zip
```

### Playbook


```yaml
- hosts: all
  become: yes
  gather_facts: yes
  roles:
    - role: common

- hosts: servers
  become: yes
  gather_facts: yes
  roles:
    - role: skydevops-java
```

License
-------

Licensed under the Apache License V2.0. See the [LICENSE file](LICENSE) for details.

## Author Information

You can find me on Twitter: [@skydevops](https://twitter.com/skydevops)

## Contributors

- Shashi Yebbare ([@skydevops](https://twitter.com/skydevops))