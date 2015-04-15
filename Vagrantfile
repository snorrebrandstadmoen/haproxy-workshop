# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # config.vm.box = "ubuntu/trusty64"
  config.vm.box = "haproxy_workshop"
  config.vm.box_url = "https://s3-eu-west-1.amazonaws.com/bekk-devops/devops-kurs.box"
  
  config.vm.network :forwarded_port, host: 4567, guest: 80

  config.vm.provision "docker" do |d|
    d.pull_images "dockerfile/java:oracle-java8"
    d.pull_images "dockerfile/nodejs"
  end
  
  config.vm.provider "virtualbox" do |vb|
     vb.memory = "4096"
  end
  config.vm.provision :shell, path: "bootstrap.sh"
end
