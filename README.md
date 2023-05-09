# Vagrant-IAAC-Static-Site-Deployment
Infrastructure As A Code Deployment of a Static Site using Vagrant on Ubuntu 20.04. The provision script below deploys a static HTML website from Tooplate onto an Ubuntu VM programmatically.

## Provision Code
```
config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
    sudo apt-get install wget unzip -y
    cd /tmp/
    wget https://www.tooplate.com/zip-templates/2134_gotto_job.zip
    unzip -o 2134_gotto_job.zip
    cp -r 2134_gotto_job/* /var/www/html/
SHELL
```
