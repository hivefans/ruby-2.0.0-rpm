# What is this spec?

Forked from imeyer's ruby-1.9.2-rpm project at https://github.com/imeyer/ruby-1.9.2-rpm and updated for 2.0.0.

This spec is an attempt to push for a stable replacement of Ruby 1.8.x with 1.9.2+ on RHEL based systems. The original author based it off of the work of [FrameOS](http://www.frameos.org) specs for Ruby 1.9.2 and Ruby Enterprise Edition.

### How to install

#### RHEL/CentOS 5/6

    yum install -y rpm-build rpmdevtools readline-devel ncurses-devel gdbm-devel tcl-devel openssl-devel db4-devel byacc
    yum install -y libyaml libyaml-devel libffi libffi-devel
    rpmdev-setuptree
    cd ~/rpmbuild/SOURCES
    wget http://cache.ruby-lang.org/pub/ruby/2.0/ruby-2.0.0-p247.tar.gz
    cd ~/rpmbuild/SPECS
    wget https://raw.github.com/hivefans/ruby-2.0.0-rpm/master/ruby200.spec
    rpmbuild -bb ruby19.spec
    
    rpm -ivh ~/rpmbuild/RPMS/x86_64/ruby-2.0.0p247-2.x86_64.rpm
    

**PROFIT!**

### What it does

+ Builds
+ Installs
+ Overwrites/upgrades your currently installed ruby package (**DANGEROUS**)

### What it does **not** do

+ Split packages into ruby-libs, ruby-devel, etc (looking for help here)
+ Install alongside Ruby 1.8.x

### Requirements

+ EPEL Yum repository (for rpmdev-setuptree)

### Distro support

Tested working (as sane as I could test for) on:

* RHEL 5.x x86_64
* RHEL 6.x x86_64
* RHEL 6.x i686
* CentOS 5.x x86_64
* Scientific Linux 6.x x86_64
