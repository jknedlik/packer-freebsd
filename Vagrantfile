# -*- mode: ruby; -*-
Vagrant.configure("2") do |config|
  config.vm.guest = :freebsd
  config.vm.box = "FreeBSD-10.1.box"
  config.vm.synced_folder ".", "/vagrant", type: "nfs"
  #
  # Un-comment the following line when working with virtualbox
  # config.vm.network "private_network", ip: "10.6.66.42"
  config.ssh.shell = "tcsh"

  config.vm.provider :vmware_fusion do |v|
    v.vmx["memsize"] = "1024"
    v.vmx["numvcpus"] = "1"
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
    vb.customize ["modifyvm", :id, "--hwvirtex", "on"]
  end
end
