# Observium with Ansible

Ansible installation of the Observium monitoring application

## Description

This code installs the application with Ansible. It is intended to be used on a blank system.

## Requirements

A recent version of Ansible is required on the control host.

The managed node can be any Linux machine, we recommend using a blank VM with Ubuntu 20.04 LTS.

## Usage

To execute the playbook on a target node, use the following command:

```shell
ansible-playbook --inventory $HOSTNAME, -e observium_domain=$FQDN site.yml
```

Replace `$HOSTNAME` with the hostname of your machine (SSH will connect to this).

Replace `$FQDN` with the fully-qualified domain name of your installation (i.e. 'observium.yourcompany.com')

### Admin Access

In order to be able to access your new Observium installation, you have to create an admin account using the command line.

Connect to your host with SSH and execute the following command:

```shell
sudo -u www-data /opt/observium/adduser.php $USER $PASSWORD 10
```

Replace `$USER` with a username of your choice and `$PASSWORD` with a secure password for the account.

## Contribution

To try out and develop the code, use Vagrant:

```shell
vagrant up
```

This will start a VM and execute the installation on it. SSH access is wrapped by the following command

```shell
vagrant ssh
```

This code is used for Freifunk Düsseldorf's own purposes.

If you have any questions, feel free to post on the [discussions page on GitHub](https://github.com/ffddorf/observium-ansible/discussions).
