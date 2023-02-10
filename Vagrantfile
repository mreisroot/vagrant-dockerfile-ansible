Vagrant.configure("2") do |config|

  # Definir o provider e alocar recursos
  config.vm.provider "virtualbox" do |v|
    v.name = "vagrant-dockerfile-ansible"
    v.cpus = 1
    v.memory = 1024
    v.gui = false
  end

  # Definir o hostname, SO e rede
  config.vm.hostname = "ubuntu"
  config.vm.box = "ubuntu/jammy64"
  config.vm.network "private_network", ip: "192.168.56.11"

  # Compartilhar a pasta em que se encontram o Playbook e as Roles do Ansible
  config.vm.synced_folder "./ansible", "/ansible"

  # Instalar o Ansible na VM
  config.vm.provision "shell", path: "provision.sh"

  # Provisionar a VM pelo Ansible
  config.vm.provision "ansible_local" do |ansible|
    ansible.provisioning_path = "/ansible"
    ansible.playbook = "playbook.yml"
  end

end
