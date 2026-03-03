Vagrant.configure("2") do |config|
  
  # VM1: Servidor DNS Maestro (maestro.empresa.local)
  config.vm.define :maestro do |maestro|
    maestro.vm.box = "Practica_0/0_vagrant"
    maestro.vm.box_version = "0.0.1"
    maestro.vm.network :private_network, ip: "192.168.50.3"
    maestro.vm.hostname = "maestro"
    maestro.vm.synced_folder "./datos_maestro", "/home/vagrant/compartido"
    maestro.ssh.insert_key = false
  end

  # VM2: Servidor DNS Esclavo (esclavo.empresa.local)
  config.vm.define :esclavo do |esclavo|
    esclavo.vm.box = "Practica_0/0_vagrant"
    esclavo.vm.box_version = "0.0.1"
    esclavo.vm.network :private_network, ip: "192.168.50.4"
    esclavo.vm.hostname = "esclavo"
    esclavo.vm.synced_folder "./datos_esclavo", "/home/vagrant/compartido"
    esclavo.ssh.insert_key = false
  end

  # Máquina Cliente para pruebas (Verificación)
  config.vm.define :cliente do |cliente|
    cliente.vm.box = "bento/ubuntu-22.04"
    cliente.vm.network :private_network, ip: "192.168.50.2"
    cliente.vm.hostname = "cliente"
    cliente.vm.synced_folder "./datos_cliente", "/home/vagrant/compartido"
    cliente.ssh.insert_key = false
  end

end
