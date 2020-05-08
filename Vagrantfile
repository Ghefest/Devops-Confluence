Vagrant.configure("2") do |config|

  config.vm.define "database" do |database|
    database.vm.box = "ubuntu/bionic64" # os
    database.vm.network "forwarded_port", guest: 4002, host: 4002
    database.vm.network "private_network", ip: "192.168.56.31"
    database.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver2", "on"]
      v.memory = "1024"
      v.name = "db"
    end
    database.vm.provision "shell", path: "provision/database-config.sh"
  end
  
  config.vm.define "confluence" do |confluence|
    confluence.vm.box = "ubuntu/bionic64"
    confluence.vm.network "forwarded_port", guest: 23332, host: 24150  
    confluence.vm.network "private_network", ip: "192.168.56.102"
    confluence.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver2", "on"]
      v.memory = "4096"
      v.name = "app"
    end
    confluence.vm.provision "shell", path: "provision/confluence-config.sh"
  end


#   config.vm.define "proxy" do |proxy|
#     proxy.vm.box = "centos/7"
#     proxy.vm.network "forwarded_port", guest: 443, host: 443, auto_correct: true
#     proxy.vm.hostname = 'proxy'
#     proxy.vm.box_url = "centos/7"

#     proxy.vm.network :private_network, ip: "192.168.56.101"
#     proxy.vm.provision "shell", path:"nginx-proxy-install.sh" 
#     proxy.vm.provider :virtualbox do |v|
#       v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
#       v.customize ["modifyvm", :id, "--memory", 512]
#       v.customize ["modifyvm", :id, "--name", "proxy"]
#     end
#   end

end
