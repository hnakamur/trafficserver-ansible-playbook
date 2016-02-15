trafficserver-ansible-playbook
==============================

My ansible playbook for testing [Apache Traffic Server](https://trafficserver.apache.org/) on a CentOS 7 Vagrant box.

## How to run

### Start a VM

```
vagrant up
```

### Add the entry to ~/.ssh/config

```
vagrant ssh-config > ssh-config
```

Copy the content of ssh-config to ~/.ssh/config and modify it like so.


```
Host local_dev
  HostName 192.168.33.131
  User root
  Port 22
  UserKnownHostsFile /dev/null
  StrictHostKeyChecking no
  PasswordAuthentication no
  IdentityFile /YOUR/PATH/TO/PLAYBOOK-DIR/.vagrant/machines/default/virtualbox/private_key
  IdentitiesOnly yes
  LogLevel FATAL
```

### Copy .envrc.example to .envrc, edit it and source it

```
cp .envrc.example .envrc
```

Edit `.envrc`.

And source it or use [direnv/direnv](https://github.com/direnv/direnv)

```
source .envrc
```

### Run ansible

```
(cd local_dev && ansible-playbook local_dev.yml)
```

## License
MIT
