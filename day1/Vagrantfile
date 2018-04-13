Vagrant.configure("2") do |config|
  config.vm.define "masternode" do |subconfig|
    subconfig.vm.box = "sbeliakou_centos.box"
    subconfig.vm.hostname = "masternode"
    subconfig.vm.network :private_network, ip: "192.168.56.10"
    subconfig.ssh.insert_key = false
    config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.name="masternode"
    end
  end

  config.vm.define "minion" do |subconfig|
    subconfig.vm.box = "sbeliakou_centos.box"
    subconfig.vm.hostname = "minion"
    subconfig.vm.network :private_network, ip: "192.168.56.20"
    subconfig.ssh.insert_key = false
    config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 1512]
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.name="minion"
    end
  end
end
