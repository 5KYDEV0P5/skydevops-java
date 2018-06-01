Ansible Role: SDJAVA
====================

This role will install and configure Oracle Java 1.8.0_171/172 on RedHat/CentOS and Debian/Ubuntu systems. 

```Note: Need to manually switch the version. [In future release thsi will be just a change of variable]
```

Requirements
------------

Require ```EPEL``` repository for redHat/CentOS machines, using ```common``` Ansible role in playbook will automatically installs EPEL repository.

Role Variables
--------------
Modify the java_version variable to install the desired version of Java
```
java_version: 1.8.0_171
```

Choose the directory in which java is installed, ```default: /apps``` if unspecified. The default directory is automatocally created by the ```common``` playbook
```
java_install_dir: /apps
```

java_src_tar: jdk-8u171-linux-x64.zip
java_home: /apps/jdk1.8.0_171
java_shared_home: /usr/shared/java
java_profile_sh: /etc/profile.d/jdk.sh



Dependencies
------------

skydevops ```common``` Ansible Role is needed, which creates the required directories and also install the required packages.

Example Playbook
----------------

Use the following playbook:

```
- hosts: all
  become: yes
  gather_facts: yes
  roles:
    - role: common

- hosts: servers
  become: yes
  gather_facts: yes
  roles:
    - role: sdjava
```

License
-------

Licensed under the Apache License V2.0. See the [LICENSE file](LICENSE) for details.

Author Information
------------------

This role was created in 2018 by [Shashi Yebbare](https://www.skydevops.co.in/), author of [SkyDevops](https://www.skydevops.co.in/).
