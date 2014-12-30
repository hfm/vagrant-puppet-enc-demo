# Demo: Puppet External Node Classifiers on Vagrant

## Setup

```sh
vagrant up
```

## Provision

```console
$ vagrant provision
==> default: Running provisioner: shell...
    default: Running: inline script
==> default: Running provisioner: puppet...
==> default: Running Puppet with init.pp...
==> default: Notice: Scope(Class[Base]): I'm included!
==> default: Notice: Compiled catalog for localhost in environment production in 0.10 seconds
==> default: Info: Applying configuration version '1419906181'
==> default: Notice: Finished catalog run in 0.04 seconds
```
