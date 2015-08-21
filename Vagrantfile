# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
sudo apt-get update
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
                        libreadline-dev libsqlite3-dev wget curl llvm \
                        libncurses5-dev
curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
pyenv update
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/vivid64"

  config.vm.provision "shell", inline: $script

  config.vm.provider "virtualbox" do |v|
      v.memory = 1024
  end
end
