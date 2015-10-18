# centos_ansible_rails
Using Ansible to provision a centos 7 machine to run ruby on rails application. 

## Overview

The purpose of this playbook is meant Penetration or Load test on a rails application server. It meant to be build, run and destroy after the testing is completed.

It was built with one command in mind to deploy the rails application to be tested.

## Basic Work
[Ansible](http://docs.ansible.com/index.html) playbook to provision a Rails deployment server with:

* Centos 7.1.5
* MySQL 5.6 (GA)
* [Phusion Passenger](https://www.phusionpassenger.com/) + nginx from Phusion's apt repo
* User Defined Ruby Version
* Prepares an nginx vhost for a Rails app, 
* Pull from Git Repo from user defined git url
* Run the rails application

## Usage ( Vagrant )

All User defined values should be stored in `vars/defaults.yml`

** Note that the current user running is vagrant ** Installation of Ruby, gems and folder for application will be placed under the current user ( vagrant ). 

Steps to use : 
  
  1. `vagrant up` where the Vagrantfile is at. 
  2. Change the hosts server IP at `hosts` file to reflect the new provision image
  2. `ansible-playbook site.yml -i hosts` to run the playbook.

## To-do 

- Tide up the home directory

- Test with creation of another user instead of using vagrant, for example a user called deployer to manage the application

- Tie up with Digital Ocean. 

- Skip ` gem install passenger ` when it is already installed

