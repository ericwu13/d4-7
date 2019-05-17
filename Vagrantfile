#-*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = 'hashicorp/precise64'

  config.vm.customize ["modifyvm", :id, "--memory", 4096]
  config.vm.customize ["modifyvm", :id, "--cpus", 4]

  config.vm.provision :shell, :inline => <<-SH
    # Packages
    export DEBIAN_FRONTEND=noninteractive
    apt-get -y update
    # apt-get -y dist-upgrade

    # zsim dependencies
    apt-get -y install build-essential g++ git scons
    apt-get -y install libelfg0-dev libhdf5-serial-dev libconfig++-dev

    # dependencies for zsim's Fortran and Java hooks (misc/hooks)
    apt-get -y install gfortran openjdk-7-jdk

    # other packages
    apt-get -y install vim
  SH
end
