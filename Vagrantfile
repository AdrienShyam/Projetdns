Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "384"
    vb.cpus = 1
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
  SHELL

  config.vm.define "dns" do |b|
    b.vm.box = "debian/contrib-stretch64"
    b.vm.hostname = "dns"
    b.vm.network "private_network", ip: "10.0.0.2"
    b.vm.network "forwarded_port", guest: 80, host: 8001
    public_key = File.read("cle_publique")

  config.vm.provision :shell, :inline =>"
     echo 'Copying ansible-vm public SSH Keys to the VM'
     mkdir -p /home/vagrant/.ssh
     chmod 700 /home/vagrant/.ssh
     echo '#{public_key}' >> /home/vagrant/.ssh/authorized_keys
     chmod -R 600 /home/vagrant/.ssh/authorized_keys
     ", privileged: false

  #  b.vm.provision "shell", path: "provision.sh", args: "dns"
  end

  config.vm.define "dnsesclave" do |b|
    b.vm.box = "debian/contrib-stretch64"
    b.vm.hostname = "dnsesclave"
    b.vm.network "private_network", ip: "10.0.0.3"
    b.vm.network "forwarded_port", guest: 80, host: 8002
     public_key = File.read("cle_publique")

  config.vm.provision :shell, :inline =>"
     echo 'Copying ansible-vm public SSH Keys to the VM'
     mkdir -p /home/vagrant/.ssh
     chmod 700 /home/vagrant/.ssh
     echo '#{public_key}' >> /home/vagrant/.ssh/authorized_keys
     chmod -R 600 /home/vagrant/.ssh/authorized_keys
     ", privileged: false
 
   # b.vm.provision "shell", path: "provision.sh", args: "dnsesclave"
  end

  config.vm.define "sauvegarde", primary: true do |b|
    b.vm.box = "debian/contrib-stretch64"
    b.vm.hostname = "sauvegarde"
    b.vm.network "private_network", ip: "10.0.0.4"
    b.vm.network "forwarded_port", guest: 80, host: 8003
     public_key = File.read("cle_publique")

  config.vm.provision :shell, :inline =>"
     echo 'Copying ansible-vm public SSH Keys to the VM'
     mkdir -p /home/vagrant/.ssh
     chmod 700 /home/vagrant/.ssh
     echo '#{public_key}' >> /home/vagrant/.ssh/authorized_keys
     chmod -R 600 /home/vagrant/.ssh/authorized_keys
     ", privileged: false

  #  b.vm.provision "shell", path: "provision.sh", args: "sauvegarde"
  end

  config.vm.define "prometheus", primary: true do |b|
    b.vm.box = "debian/contrib-stretch64"
    b.vm.hostname = "prometheus"
    b.vm.network "private_network", ip: "10.0.0.5"
    b.vm.network "forwarded_port", guest: 80, host: 8004
     public_key = File.read("cle_publique")

  config.vm.provision :shell, :inline =>"
     echo 'Copying ansible-vm public SSH Keys to the VM'
     mkdir -p /home/vagrant/.ssh
     chmod 700 /home/vagrant/.ssh
     echo '#{public_key}' >> /home/vagrant/.ssh/authorized_keys
     chmod -R 600 /home/vagrant/.ssh/authorized_keys
     ", privileged: false

  #  b.vm.provision "shell", path: "provision.sh", args: "prometheus"
  end

  config.vm.define "dnsesclave-roundrobind", primary: true do |b|
    b.vm.box = "debian/contrib-stretch64"
    b.vm.hostname = "dnsesclave-roundrobind"
    b.vm.network "private_network", ip: "10.0.0.6"
    b.vm.network "forwarded_port", guest: 80, host: 8005
     public_key = File.read("cle_publique")

  config.vm.provision :shell, :inline =>"
     echo 'Copying ansible-vm public SSH Keys to the VM'
     mkdir -p /home/vagrant/.ssh
     chmod 700 /home/vagrant/.ssh
     echo '#{public_key}' >> /home/vagrant/.ssh/authorized_keys
     chmod -R 600 /home/vagrant/.ssh/authorized_keys
     ", privileged: false

  #  b.vm.provision "shell", path: "provision.sh", args: "dnsesclave-roundrobind"
  end
  config.vm.define "client", primary: true do |b|
    b.vm.box = "debian/contrib-stretch64"
    b.vm.hostname = "client"
    b.vm.network "private_network", ip: "10.0.0.7"
    b.vm.network "forwarded_port", guest: 80, host: 8006
     public_key = File.read("cle_publique")

  config.vm.provision :shell, :inline =>"
     echo 'Copying ansible-vm public SSH Keys to the VM'
     mkdir -p /home/vagrant/.ssh
     chmod 700 /home/vagrant/.ssh
     echo '#{public_key}' >> /home/vagrant/.ssh/authorized_keys
     chmod -R 600 /home/vagrant/.ssh/authorized_keys
     ", privileged: false

  #  b.vm.provision "shell", path: "provision.sh", args: "client"
  end
end
