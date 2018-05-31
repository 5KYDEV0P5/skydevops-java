SDJAVA
=========

This role will install and configure Oracle Java 1.8.0_171/172. Need to manually switch the version. [In future release thsi will be just a change of variable]

Requirements
------------

```common``` role is the dependency, which will setup the directory structure and install pre-requisites

Role Variables
--------------
```
---

java_version: 1.8.0_171
java_install_dir: /apps
java_src_tar: jdk-8u171-linux-x64.zip
java_home: /apps/jdk1.8.0_171
java_shared_home: /usr/shared/java
java_profile_sh: /etc/profile.d/jdk.sh
```


Dependencies
------------

skydevops ```common``` Ansible Role is needed

Example Playbook
----------------

Use the following playbook:

```
- hosts: test_servers
  become: yes
  gather_facts: yes
  roles:
    - role: common
    - role: sdjava
      tags: java
    - role: maven
      tags: maven
```

License
-------

Licensed under the Apache License V2.0. See the [LICENSE file](LICENSE) for details.

Author Information
------------------

Author: Shashi yebbare
