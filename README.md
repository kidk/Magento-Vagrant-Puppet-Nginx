Magento-Vagrant-Puppet-Nginx
============================

## Installs

* Magento
* MySQL
* PHP
* PHP-FPM
* Nginx
* n98-magerun

## Setup

``` sh
git submodule init
git submodule update
vagrant up
```

Modify puppet/manifests/base.pp


``` puppet
class { "magento":
  install_magento     => true,
  magento_version     => "magento-ce-1.8.1.0",
  install_sample_data => true
}
```

Valid Magento Versions:

* magento-mirror-1.9.2.2
* magento-mirror-1.9.2.1
* magento-mirror-1.9.2.0
* magento-mirror-1.9.1.1
* magento-mirror-1.9.1.0
* magento-mirror-1.9.0.1
* magento-mirror-1.9.0.0
* magento-mirror-1.8.1.0
* magento-mirror-1.8.0.0
* magento-mirror-1.7.0.2
* magento-mirror-1.6.2.0
* magento-mirror-1.5.1.0
* magento-mirror-1.4.2.0

## Frontend

After Installation you should can access the shop frontend over port 8080.

http://127.0.0.1:8080

## Admin

http://127.0.0.1:8080/admin

```
Username: admin
Password: password123
```


To change the admin login you can use n98-magerun.

``` bash
vagrant ssh
cd /vagrant
n98-magerun.phar admin:user:change-password admin mypassword
```   
