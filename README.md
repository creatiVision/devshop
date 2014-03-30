DevShop Vagrant
===============

This project contains a Vagrantfile for launching a devshop virtual machine.

It uses the stock [install-ubuntu.sh](https://github.com/drupaldevshop/devshop/blob/6.x-1.x/install.debian.sh)
file in the devshop project so that deployed servers and vagrant boxes are the same.

Dependencies
------------

- Git
- Vagrant 1.5.x
- VirtualBox (or any supported virtualization software like VMWare)

Setup
-----

To get started with this project, you need to setup the right versions of it's dependencies.

Some of you may have these things, so just make sure they are up to date.

It is best to use the installers from the websites so you are sure to get the right version.


1. Install Vagrant.
  Available at [http://www.vagrantup.com/downloads.html](http://www.vagrantup.com/downloads.html).
  
  *Use version 1.5.x and up.*

2. Install VirtualBox.
  Available at [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
  
  *Use version 4.3.x and up.*

3. Install Git.
  Available at [http://www.gitscm.com/](http://www.gitscm.com/)

  *Any version is probably fine.*

4. Edit your local hosts file.
  You need to edit your computers `/etc/hosts` file to reach [devshop.local](http://devshop.local).
  The IP is defined in `attributes.json` and is 10.10.10.10 by default.

  Add this line to your `/etc/hosts` file:
  
  ```
  10.10.10.10  devshop.local
  ```
  @TODO: Try out [vagrant-hosts plugin](https://github.com/adrienthebo/vagrant-hosts).
  
5. Clone this Repo.

  ```
  git clone git@github.com:drupaldevshop/devshop_vagrant.git
  ```
6. Vagrant Up!
  ```
  cd devshop_vagrant vagrant up
  ```
  Once the install script finished you should see the stock DevShop Install Success output 
  with a link to login to your devshop front-end.

  *You must use that link to login.* The admin password is automatically generated.
  
7. Manage Devshop.

  To access the server simply use `vagrant ssh`, then switch to the `aegir` user:
  ```
  sudo su - aegir
  ```
  Once you are the aegir user, you can interact with the devshop front-end with drush.  For example, 
  to get another login link, use the `drush uli` command:
  ```
  drush @hostmaster uli
  ```
  All server-side interactions with your sites are done as the `aegir` user.
  
  
*NOTE: When you create new projects and environments, you will need to add those URIs to your 
hosts file as well, or you will not be able to access them.*

Development
-----------

If you are interested in developing devshop, checkout the `/repos` folder.

