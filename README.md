Belfast Bootstrap
=================

Pre-reqs
--------

### Install Ansible

```
$ xcode-select --install
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install ansible
```

### Usage

```
ansible-playbook main.yml
```

After this completes, the terminal will be killed.  To complete the install run:

```
ansible-playbook post.yml
```
