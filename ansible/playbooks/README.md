#### execute playbooks
### Required:
1. VirtualBox
2. Vagrant
3. Ansible

#### Download and add centos/7 box, support for other OS can be added later
```
vagrant box add centos/7 https://app.vagrantup.com/centos/boxes/7
```

#### install ansible
```
sudo easy_install pip
sudo pip install ansible
```

#### as the first step run
```
ssh-keygen
```
```
ansible-playbook ambari-prereqs.yml --private-key=field.pem -f 5 --sudo
ansible-playbook ambari-agent.yml --private-key=field.pem -f 5 --sudo
```

#### requires /etc/ansible/hosts to include ambari-server at the minimum
#### or see inventory file for example
```
[nodes]
aervits-hdp[0:7].field.hortonworks.com

[ambari-server]
aervits-hdp0.field.hortonworks.com
```

#### TODO
1. add REST call to add user-post-creation-hook
2. add REST call to add user to ambari

