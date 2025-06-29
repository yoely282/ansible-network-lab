Vagrant.configure("2") do |config|
  config.vm.box = "perk/ubuntu-2204-arm64"
  config.vm.provider "qemu"

  config.vm.define "ubuntu1" do |node|
    node.vm.hostname = "ubuntu1"
    node.vm.network "private_network", type: "dhcp"
    node.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y openssh-server python3
    SHELL
  end

  config.vm.define "ubuntu2" do |node|
    node.vm.hostname = "ubuntu2"
    node.vm.network "private_network", type: "dhcp"
    node.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y openssh-server python3
    SHELL
    # Override the SSH port manually (optional)
    node.vm.provider "qemu" do |qemu|
      qemu.functional = true
    end
  end
end

