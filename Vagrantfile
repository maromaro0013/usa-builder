config.vm.define "usa-games.local" do | node |
  node.vm.hostname = "usa-games"
  node.vm.box = "mvbcoding/awslinux"
  node.vm.network :private_network, ip: "192.168.33.104"
  node.vm.network "forwarded_port", guest: 22, host: 2040, id: "ssh"
  node.vm.synced_folder ".", "/vagrant", type: "nfs", :mount_options => ['nolock,vers=3,udp']

  node.vm.provider :virtualbox do | vb |
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "off"]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "off"]
    vb.customize ["setextradata", :id, "VBoxInternal/Devices/VMMDev/0/Config/GetHostTimeDisabled", 1]
  end
end
