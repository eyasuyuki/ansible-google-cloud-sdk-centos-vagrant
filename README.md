# Requirements

- Ansible
- Vagrant

# Clone this repository

```
git clone git@github.com/eyasuyuki/ansible-google-cloud-platform-centos6-vagrant.git
```

# Initialize Vagrant box

```
cd ansible-google-cloud-platform-centos6-vagrant
vagrant init centos6
vagrant up
```

# Test Ansible


```
ansible all -u vagrant -m shell -a "ps axu" -vvvv --private-key=.vagrant/machines/default/virtualbox/private_key
```

# Install Google Cloud SDK to Vagrant host

```
ansible-playbook setup.yml -vvvv --private-key=.vagrant/machines/default/virtualbox/private_key
```

It installs only root user, without vagrant user.

Note: CLOUDSDK_INSTALL_DIR environment value is set to /usr/local in roles/sdk/tasks/main.yml.
If you want to install to another directory, please put you own.
