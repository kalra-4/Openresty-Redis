Vagrant.configure("2") do |config|
  config.vm.box_check_update = false
  config.vm.synced_folder "files", "/etc/nginx", type: "rsync"

  config.vm.define :node1 do |node|
  node.vm.box = "centos/7"
   node.vm.network "private_network", ip: "10.0.0.10"
end

  config.vm.define :node2 do |node|
  node.vm.box = "centos/7"
   node.vm.network "private_network", ip: "10.0.0.20"
end

   config.vm.provider "virtualbox" do |vb|
#     vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
     vb.gui = false
     vb.memory = "2048"
     vb.cpus = "2"
end

  config.vm.provision "shell" do |s|
   s.inline = <<-SHELL
      yum -y install libselinux-python
      SHELL
  end

end
