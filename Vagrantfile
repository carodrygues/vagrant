
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"

  config.vm.define "mysqlserver" do |mysqlserver|

    mysqlserver.vm.network "forwarded_port", guest: 3306, host: 3308

    mysqlserver.vm.provider "virtualbox" do |vb|
      vb.name = "mysqlserver"
      vb.memory = 2048
      vb.cpus =  2
    end
    mysqlserver.vm.provision "shell", inline: "apt-get update && apt-get install -y mysql-server-5.7"
  end
end