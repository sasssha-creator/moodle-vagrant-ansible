Vagrant.configure("2") do |config|
  # Офіційний образ Ubuntu 22.04 LTS
  config.vm.box = "ubuntu/jammy64"
  
  # Локальна IP-адреса для доступу до Moodle з хост-комп'ютера
  config.vm.network "private_network", ip: "192.168.56.10"
  
  # Виділення ресурсів віртуальної машини
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
    vb.gui = true
  end

  # Інструкція для Vagrant: встановити Ansible всередину Ubuntu і запустити плейбук
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.install_mode = "pip"
  end
end