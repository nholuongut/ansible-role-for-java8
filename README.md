# Install and configure java on your system.

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/nholuongut/ansible-role-for-java8/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: robertdebock.java
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/nholuongut/ansible-role-for-java8/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Default
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: robertdebock.bootstrap
```

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/nholuongut/ansible-role-for-java8/blob/master/defaults/main.yml):

```yaml
---
# defaults file for java

# Set the vendor of java, valid values are "openjdk" and "oracle".
java_vendor: openjdk

# Set the variable to install the type, valid values are "jre" and "jdk".
java_type: jre

# Set the version of java, valid values are 6, 7, 8, 9, 10, 11, 12 or 13.
# By default, a distibution default is used, mapped in `vars/main.yml`.
# By setting java_version, you overwrite this default to your selected
# version.
java_version: "{{ java_default_version }}"

# Set the format of the installation source, valid values are "targz" and
# "rpm". This is only valid with "java_vendor == oracle"
java_format: targz

# Where do the RPMs come from when installing Oracle RPMs?
# Either "local" or "repository".
# Valid for "java_vendor == oracle" and "java_format" == "rpm"
java_rpm_source: local

# Choose if you can JCE installed. Only applicable for (both):
# - java_vendor == "oracle"
# - java_version == "8"
java_jce: yes

# In case of "java_vendor == oracle" and "java_format == targz", a directory
# as to be set where to install.
java_install_directory: /opt
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/nholuongut/ansible-role-for-java8/blob/master/requirements.txt).

## [Context](#context)

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/nholuongut/ansible-role-for-java8/png/requirements.png "Dependencies")


The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
