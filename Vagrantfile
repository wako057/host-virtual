# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.define "api-marvel-01" do |api01|
    api01.vm.box = "hashicorp/bionic64"
    api01.vm.hostname =  "api-marvel-01.wako057.net"
    api01.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--cpus", 2]
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "api-marvel-01.wako057.net"]
    end
    api01.vm.network "private_network", ip: "192.168.33.42"
    api01.vm.provision "file", source: "~/.ssh/id_rsa_rundeck.pub", destination: "~/.ssh/me.pub"
    api01.vm.provision "shell", inline: <<-SHELL
    cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end

  config.vm.define "api-marvel-02" do |api02|
    api02.vm.box = "hashicorp/bionic64"
    api02.vm.hostname =  "api-marvel-02.wako057.net"
    api02.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--cpus", 2]
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "api-marvel-02.wako057.net"]
    end
    api02.vm.network "private_network", ip: "192.168.33.43"
    api02.vm.provision "file", source: "~/.ssh/id_rsa_rundeck.pub", destination: "~/.ssh/me.pub"
    api02.vm.provision "shell", inline: <<-SHELL
    cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end

end
