# hermit-crab

Develop with less fear! Quickly provision a clean virtual environment kitted
out for development.

## Overview

Attempting to keep your OS clean of the cruft that builds up during software
development is a near impossible task. `hermit-crab` automates the drudge work
of building new 'disposable' environments.

It uses [Vagrant][vagrant] with [Ansible][ansible] to manage the
[configuration][config] and [provisioning][provision] of a virtual machine for
development. It's a recipe that reflects my preferences and opinions, but will
hopefully mature into a project that could be forked and easily adjusted to
another's tastes.

## Provides

- Ubuntu 14.04 Server LTS
- Dirt simple Ansible scripts written with a single user/machine in mind
- Minimal Lubuntu desktop
- VirtualBox Guest Additions
- Avahi to register itself on LAN at `hermit.local`
- Ruby, NodeJS, and Java 8 runtimes
- [rbenv][rbenv], [nvm][nvm], [lein][lein], [boot-clj][boot]
- dotfiles and useful `~/bin` tools
- Vim + Emacs!

## Usage

    $ git clone https://github.com/tvjg/hermit-crab
    $ cd hermit-crab
    $ vagrant up

    Reboot for VirtualBox Guest Additions to take effect.
    $ vagrant reload

The VM is configured to run with a GUI. You can enter the default
username/password `vagrant:vagrant` on the login screen. Alternately, use
`vagrant ssh` from the project directory.

## TODO

- [ ] Add project repository list to pull on provision
- [ ] Extract more configuration to vars
- [x] Add Ansible tags to toggle package configuration
- [ ] Make it easy to share SSH keys from host
- [ ] Enable unattended security updates
- [ ] Investigate alternate desktop environments
- [ ] Restore ansible workaround for Windows
- [ ] Avahi instructions for Windows

[vagrant]: https://www.vagrantup.com/ 
[ansible]: http://www.ansible.com/about
[rbenv]: https://github.com/sstephenson/rbenv
[nvm]: https://github.com/creationix/nvm
[boot]: https://github.com/boot-clj/boot
[config]: http://docs.vagrantup.com/v2/why-vagrant/index.html
[provision]: http://en.wikipedia.org/wiki/Provisioning#Server_provisioning
[lein]: https://github.com/technomancy/leiningen 
