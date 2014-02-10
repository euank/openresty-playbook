openresty-playbook
==================

A playbook role for setting up the OpenResty nginx bundle on CentOS

Tested on CentOS 6.5

Usage
=====

This isn't actually a complete playbook since it never maps hosts to roles.
However, it's basically there. The following will make it a complete one:

```
mkdir roles
git clone https://github.com/euank/openresty-playbook.git roles/openresty
```

And then create fhe file `run.yml` in the current directory (name it as you
like) with the following contents:

```
---
- hosts: openresty
  sudo: true
  roles:
    - openresty
```

Change the `hosts` line to whatever you do name your group for openresty.

This is meant to be a reusable component to git submodule into another playbook.

Issues
------

Realistically if you wanted to install openresty on a bunch of nodes you should
create an rpm or deb or other binary package and distribute that. This is
intended for smaller projects where you don't need to worry so much about doing
it the "right" way for scale.
