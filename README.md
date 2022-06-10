## Link to blog article

https://nickvsnetworking.com/testing-mobile-networks-with-remote-test-phones/

## Remote Android UE Tester

This Ansible Playbook builds the enviroment to run remote Android devices for the purposes of testing cellular networks remoteley.

The target OS is Debian 10 / 11 or Raspbian.

### Playbook Usage

These hosts are defined in the ``hosts.yml`` file, which is populated with the detials of all of these.

When the hosts file is Populated the Ansible Playbook itself can be run in order to setup and configure these hosts. It is run with:

```ansible-playbook remote_android_ue_tester.yml -i hosts.yml```

Example hosts file:
```

remote_ue_testers:
  hosts:
    remote-ue-tester-003-BTSsiteID-01:
      ansible_host: 10.0.1.4
      ansible_user: nick
      ansible_connection: ssh
      ansible_ssh_pass: password
      become_user: root 
      ansible_become_password: password
  vars:
    ansible_ssh_common_args: '-o StrictHostKeyChecking=no'


```
