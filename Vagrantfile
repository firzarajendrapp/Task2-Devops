Vagrant.configure("2") do |config|
config.vm.box = "bento/ubuntu-20.04"
  config.vm.network "forwarded_port", guest: 5000, host: 5000

  config.vm.network "private_network", ip: "10.10.10.20"

  config.vm.define "trusty" do |node|
    node.vm.hostname = "trusty.local"
  end
  config.vm.provision "ansible_local" do |ansible|
    ansible.install = true
    ansible.playbook = "main.yml"
  end
config.vm.provider "virtualbox" do |vb|
vb.memory = "1024"
     vb.cpus = "2"
   end
config.vm.provision "shell", inline: <<-SHELL
     apt-get update

   SHELL
end
