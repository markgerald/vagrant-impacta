
Vagrant.configure("2") do |config|
  config.vm.box = "base"
  config.vm.box = "ubuntu/bionic64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
    vb.cpus = 1
  end
  config.vm.define "mysql-server" do |db|
      db.vm.network "public_network", :bridge => "eth0", ip: "192.168.1.237"
      db.vm.network "forwarded_port", guest: 3306, host: 3306
      db.vm.network "forwarded_port", guest: 80, host: 8080
      db.vm.provision "shell", path: "bootstrap.sh"
  end

end
