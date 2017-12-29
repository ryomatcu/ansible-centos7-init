# ansible-centos7-init
Initial setup for CentOS7 with Ansible.

# Description

This playbook provides initial setup and install httpd for CentOS7.

configures:

* yum update
* yum groupinstall "Development Tools"
* set locale
* set timezone
* install httpd
* add firewalld rule (http)

# Usage

Copy inventories.sample to inventories.

```
$ cp inventories.sample inventories
```

Change host ip address.

```
[mycentos]
192.168.1.100
```

Change configuration information in setup.yml

```
  remote_user: ops
  ...
  vars:
    - locale: ja_JP.utf8
    - timezone: Asia/Tokyo
```

Execute command

```
$ ansible-playbook -i inventories setup.yml --ask-pass --ask-su-pass
```

