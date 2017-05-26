# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
sudo apt-get update
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
                        libreadline-dev libsqlite3-dev wget curl llvm \
                        libncurses5-dev
curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
echo 'export PATH="/home/vagrant/.pyenv/bin:$PATH"' > $HOME/.bash_profile
echo 'eval "$(pyenv init -)"' >> $HOME/.bash_profile
echo 'eval "$(pyenv virtualenv-init -)"' >> $HOME/.bash_profile
pyenv update
pyenv install 3.3.6
pyenv global 3.3.6
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "minimal/xenial64"

  config.vm.provision "shell", inline: $script

  config.vm.provider "virtualbox" do |v|
      v.memory = 1024
  end
end
