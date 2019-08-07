Vagrant.configure("2") do |config|
	config.vm.box = "centos/7"
	config.vm.network "private_network", ip: "10.0.0.102"
	config.vm.hostname = "centos102"
	config.vm.provision "shell", inline: <<-SHELL
	sed -i s/^SELINUX=.*$/SELINUX=disabled/ /etc/selinux/config
	systemctl disable firewalld
  sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config    
  reboot
 SHELL
end