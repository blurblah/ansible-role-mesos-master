# ansible-role-mesos-master
This role supports only for Ubuntu 14.04 and 16.04 and tested on Ansible version 2.4.2

## Playbook sample
This playbook installs mesos-masters.
```yaml
- hosts: mesos-masters
  become: yes
  roles:
    - role: mesos-master
      quorum: 2
      mesos_masters:
        - { server_id: 1, host: 192.168.0.10, zk_port: 2181, election_port1: 2888, election_port2: 3888 }
        - { server_id: 2, host: 192.168.0.11, zk_port: 2181, election_port1: 2888, election_port2: 3888 }
        - { server_id: 3, host: 192.168.0.12, zk_port: 2181, election_port1: 2888, election_port2: 3888 }
      java_opts:
        - "-Xms1024m"
        - "-Xmx1024m"
```

