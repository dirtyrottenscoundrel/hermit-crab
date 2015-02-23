# hermit-crab

Develop with less fear! Quickly provision a clean virtual environment kitted
out for development.

## Overview

Attempting to keep an operating system clean of the cruft that builds up during
software development is a near impossible task. `hermit-crab` automates the
drudge work of building a new 'disposable' environment.

It uses [Vagrant][vagrant] with [Ansible][ansible] to manage the
[configuration][config] and [provisioning][provision] of a virtual machine for
development. It is a recipe that reflects my preferences and opinions, but will
hopefully mature into a project that could be forked and easily adjusted to
another's tastes.

## Features

- Ubuntu 14.04 Server LTS
- Dirt simple Ansible scripts written with a single user/machine in mind
- Minimal Gnome 3 desktop
- VirtualBox Guest Additions
- Uses Avahi to register itself on LAN at `<hostname>.local`
- Ruby, NodeJS, and Java 8 runtimes
- [rbenv][rbenv], [nvm][nvm], [boot-clj][boot]
- Provisions dotfiles and useful `~/bin` tools
- Vim + Emacs!

## Usage

    $ git clone https://github.com/dirtyrottenscoundrel/hermit-crab
    $ cd hermit-crab
    $ vagrant up
    $ vagrant provision

The VM is configured to run with a GUI. You can enter the default
username/password `vagrant:vagrant` on the login screen. Alternately, use
`vagrant ssh` from the project directory.

## TODO

- [ ] Add project repository list to pull on provision
- [ ] Extract more configuration to vars
- [ ] Add Ansible tags to toggle package configuration from the Vagrantfile
- [ ] Make it easy to share SSH keys from host
- [ ] Enable unattended security updates
- [ ] Investigate alternate desktop environments

[vagrant]: https://www.vagrantup.com/ 
[ansible]: http://www.ansible.com/about
[rbenv]: https://github.com/sstephenson/rbenv
[nvm]: https://github.com/creationix/nvm
[boot]: https://github.com/boot-clj/boot
[config]: http://docs.vagrantup.com/v2/why-vagrant/index.html
[provision]: http://en.wikipedia.org/wiki/Provisioning#Server_provisioning
