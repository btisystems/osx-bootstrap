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

### Setup SSH

For every client machine, we need to have Remote Sharing setup and use ssh-copy-id to use locally available keys to authorise logins on a remote machine, for e.g.

```
$ ssh-copy-id admin@172.27.2.189
```

Usage
-----

```
$ ansible-playbook main.yml
```

Problem 1
---------

fatal: [172.27.2.189]: FAILED! => {"changed": false, "failed": true, "msg": "Error: Permission denied - /usr/local/Library/Formula/.gitignore20160210-866-1176cw6"}

This is a permission issue with /usr/local, this can be resolved by setting the directory permissions correctly on the client machine.

SSH to the machine with the user with admin privileges.

```
$ sudo chown -R $USER:admin /usr/local
```

Problem 2
---------

fatal: [172.27.2.189]: FAILED! => {"changed": false, "failed": true, "msg": "Error: Permission denied - /Library/Caches/Homebrew/Formula/pcre.brewing"}

```
$ sudo chown -R $USER:admin /Library/Caches/Homebrew/
$ sudo chmod -R g+w /Library/Caches/Homebrew
```
