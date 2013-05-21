# A Virtual Machine for the Tested Scaling with Rails Workshop

## Introduction

This project automates the setup of a development environment for general Ruby on Rails application development.

Based on [https://github.com/amaia/rails-starter-box](https://github.com/amaia/rails-starter-box).

## Requirements

* [VirtualBox](https://www.virtualbox.org)

* [Vagrant](http://vagrantup.com)

## How To Build The Virtual Machine

Building the virtual machine is this easy:

    host $ git clone https://github.com/walski/salzburg-box.git
    host $ git submodule init
    host $ git submodule update
    host $ cd salzburg-box
    host $ vagrant up

If the base box is not present that command fetches it first.

    host $ vagrant ssh
    Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic-pae i686)
    ...
    vagrant@rails-starter-box:~$

Port 30000 in the host computer is forwarded to port 3000 in the virtual machine. Thus, applications running in the virtual machine can be accessed via localhost:30000 in the host computer.

## What's In The Box

* Git

* SQLite3, MySQL, and Postgres

* RVM (with ruby 1.9.3 and 1.8.7, JRuby and REE installed)

* Bundler, Rails and Rake gems for all rubies

* Thin, Unicorn and Puma app servers

* A sample app

* ab, httperf and gnuplot tools


## Recommended Workflow

The recommended workflow is

* edit files in the host computer

* run within the virtual machine


## Virtual Machine Management

When done just log out with and suspend the virtual machine

    host $ vagrant suspend

then, resume to hack again

    host $ vagrant resume

Run

    host $ vagrant halt

to shutdown the virtual machine, and

    host $ vagrant up

to boot it again.

You can find out the state of a virtual machine anytime by invoking

    host $ vagrant status

Finally, to completely wipe the virtual machine from the disk **destroying all its contents**:

    host $ vagrant destroy # DANGER: all is gone

Please check the [Vagrant documentation](http://vagrantup.com/v1/docs/index.html) for more information on Vagrant.
