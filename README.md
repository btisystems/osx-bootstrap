Belfast Bootstrap
=================

Pre-reqs
--------

### Install Ansible

```
xcode-select --install
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install ansible
```

### Usage

```
ansible-playbook --ask-become-pass main.yml
```

After this completes, the terminal will be killed signalling the end of the playbook run.
