# Ubuntu-WPIaaC

Ubuntu WordPress IaaC, This is just a simple vagrantfile script for you to deploy automatically Apache2, Mysql, and WordPress on your Ubuntu 20.04 Box in your Vagrant-vms.

## Installation

Use git clone.
```bash
git clone https://github.com/oepilcore/Ubuntu-WPIaaC.git
```
Copy the file to your vagrant-vms folder
*For example mine folder was installed on drive D
```bash
mv Ubuntu-WPIaaC /d/vagrant-vms/
```

## Usage

```bash
cd /vagrant-vms/Ubuntu-WPIaaC
vagrant up
```

## Note

Please take note of some lines:
Change these lines using your private IP
```bash
config.vm.network "private_network", ip: "xxx.xxx.xxx.xxx"
```

Change these lines to using your DB Password
```bash
mysql -u root -e 'CREATE USER wordpress@localhost IDENTIFIED BY "<insert your password here>";'
```

And another line you need to replace the password that you created before with this line
```bash
sudo -u www-data sed -i 's/password_here/<your-password-here>/' /srv/www/wordpress/wp-config.php
```

## Source
[Ubuntu Install and Configure WordPress](https://discourse.ubuntu.com/t/install-and-configure-wordpress/13959)
