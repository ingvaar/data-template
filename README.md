# Data project template

Based on specifications by [@foxygat](https://github.com/foxygat).

This template uses [Vagrant](https://www.vagrantup.com/) to ensure a clean and consistent work environment.
Learn more how to use it in the [quick start](#quick-start) section.

This Vagrant environment comes with [Jupyter](https://jupyter.org/) preinstalled along with `Python 3` and a `virtualenv`.
The `workspace` directory is shared with Vagrant: everything in it will be persistent.

## Quick Start

For the quick-start, we'll use [VirtualBox](https://www.virtualbox.org/) because it is free and workson all major platforms.
Vagrant can, however, work with almost any system such as [OpenStack](https://www.openstack.org/), [VMware](https://www.vmware.com/), [Docker](https://docs.docker.com/), etc.

First, make sure your development machine has [VirtualBox](https://www.virtualbox.org/) installed. After this, [download and install the appropriate Vagrant package for your OS](https://www.vagrantup.com/downloads.html).

To bring up the environment, use:

    vagrant up

To pause the environment, use:

    vagrant suspend

To resume the environment, use:

    vagrant resume

To destroy and clean the environment, use:

    vagrant destroy

> Note that everything inside the workspace environment will be persistent, even after a destroy.
> Everything else will be lost.

You can discover all commands available using the `vagrant -h` command.

