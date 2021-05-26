
Vagrant.configure(2) do |config|
  #ansible = <<-ANSIBLE
  #yum -y install ansible
  #ANSIBLE
  common = <<-SCRIPT
  if ! grep -q controlz /etc/hosts; then  sudo echo "192.168.56.120     controlz" >> /etc/hosts ;fi
  if ! grep -q node01 /etc/hosts; then  sudo echo "192.168.56.121     node01" >> /etc/hosts ;fi
  if ! grep -q node02 /etc/hosts; then  sudo echo "192.168.56.122     node02" >> /etc/hosts ;fi
  if ! grep -q node03 /etc/hosts; then  sudo echo "192.168.56.123     node03" >> /etc/hosts ;fi
  if ! grep -q node04 /etc/hosts; then  sudo echo "192.168.56.124     node04" >> /etc/hosts ;fi
  if ! grep -q node05 /etc/hosts; then  sudo echo "192.168.56.125     node05" >> /etc/hosts ;fi
  if ! grep -q node06 /etc/hosts; then  sudo echo "192.168.56.126     node06" >> /etc/hosts ;fi
  if ! id admin >  /dev/null 2>&1 ; then sudo useradd -G 10 -p $(openssl passwd -1 redhat) admin; fi
  if [ ! -f /etc/sudoers.d/admin ] ; then sudo echo "admin        ALL=(ALL)       NOPASSWD: ALL" > /etc/sudoers.d/admin ; fi
  sudo yum -y install vim tree net-tools telnet git python-pip
  sudo echo "autocmd filetype yaml setlocal ai ts=2 sw=2 et" > /home/devops/.vimrc
  SCRIPT
  
  #ansible_control_node = <<-SCRIPT
  #SCRIPT

	config.vm.box = "centos7lab"
	config.vm.box_url = "https://github.com/CommanderK5/packer-centos-template/releases/download/0.7.2/vagrant-centos-7.2.box"

	config.vm.define "controlz" do |control|
		control.vm.hostname = "controlz"
		control.vm.network "private_network", ip: "192.168.56.120"
		control.vm.provider "virtualbox" do |v|
			v.customize [ "modifyvm", :id, "--cpus", "1" ]
			v.customize [ "modifyvm", :id, "--memory", "312" ]
		end
		#config.vm.provision :shell, :inline => ansible
		config.vm.provision :shell, :inline => common
		#config.vm.provision "ansible_local" do |ansible|
		#	ansible.playbook = "playbook.yml"
		#end
	end
	config.vm.define "node01" do |node1|
		node1.vm.hostname = "node01"
		node1.vm.network "private_network", ip: "192.168.56.121"
		node1.vm.provider "virtualbox" do |v|
			v.customize [ "modifyvm", :id, "--cpus", "2" ]
			v.customize [ "modifyvm", :id, "--memory", "2000" ]
		end
		#config.vm.provision :shell, :inline => ansible
		config.vm.provision :shell, :inline => common
		#config.vm.provision "ansible_local" do |ansible|
		#	ansible.playbook = "playbook.yml"
		#end
	end
	config.vm.define "node02" do |node2|
		node2.vm.hostname = "node02"
		node2.vm.network "private_network", ip: "192.168.56.122"
		node2.vm.provider "virtualbox" do |v|
			v.customize [ "modifyvm", :id, "--cpus", "2" ]
			v.customize [ "modifyvm", :id, "--memory", "2000" ]
		end
		#config.vm.provision :shell, :inline => ansible
		config.vm.provision :shell, :inline => common
		#config.vm.provision "ansible_local" do |ansible|
		#	ansible.playbook = "playbook.yml"
		#end
	end
	config.vm.define "node03" do |node3|
		node3.vm.hostname = "node03"
		node3.vm.network "private_network", ip: "192.168.56.123"
		node3.vm.provider "virtualbox" do |v|
			v.customize [ "modifyvm", :id, "--cpus", "2" ]
			v.customize [ "modifyvm", :id, "--memory", "2000" ]
		end
		#config.vm.provision :shell, :inline => ansible
		config.vm.provision :shell, :inline => common
		#config.vm.provision "ansible_local" do |ansible|
		#	ansible.playbook = "playbook.yml"
		#end
	end
	config.vm.define "node04" do |node4|
		node4.vm.hostname = "node04"
		node4.vm.network "private_network", ip: "192.168.56.124"
		node4.vm.provider "virtualbox" do |v|
			v.customize [ "modifyvm", :id, "--cpus", "1" ]
			v.customize [ "modifyvm", :id, "--memory", "2000" ]
		end
		#config.vm.provision :shell, :inline => ansible
		config.vm.provision :shell, :inline => common
		#config.vm.provision "ansible_local" do |ansible|
		#	ansible.playbook = "playbook.yml"
		#end
	end
	config.vm.define "node05" do |node5|
		node5.vm.hostname = "node05"
		node5.vm.network "private_network", ip: "192.168.56.125"
		node5.vm.provider "virtualbox" do |v|
			v.customize [ "modifyvm", :id, "--cpus", "1" ]
			v.customize [ "modifyvm", :id, "--memory", "2000" ]
		end
		#config.vm.provision :shell, :inline => ansible
		config.vm.provision :shell, :inline => common
		#config.vm.provision "ansible_local" do |ansible|
		#	ansible.playbook = "playbook.yml"
		#end
	end
		config.vm.define "node06" do |node6|
		node6.vm.hostname = "node06"
		node6.vm.network "private_network", ip: "192.168.56.126"
		node6.vm.provider "virtualbox" do |v|
			v.customize [ "modifyvm", :id, "--cpus", "1" ]
			v.customize [ "modifyvm", :id, "--memory", "2000" ]
		end
		#config.vm.provision :shell, :inline => ansible
		config.vm.provision :shell, :inline => common
		#config.vm.provision "ansible_local" do |ansible|
		#	ansible.playbook = "playbook.yml"
		#end
	end

end