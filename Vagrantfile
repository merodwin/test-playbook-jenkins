Vagrant.configure("2") do |config|

  # As eNform VM depends on Oracle install OracleVM first
  config.vm.define "jenkins" do |jenkins|
	jenkins.vm.box = "ubuntu/trusty64"
	jenkins.vm.network "private_network", ip: "10.1.1.2"
        jenkins.ssh.username = "vagrant"
        jenkins.ssh.password = "vagrant"
	jenkins.vm.provider "virtualbox" do |vb|
#		vb.gui = true
		vb.memory = "2048"
		vb.cpus = "2"
	end
  end

  config.vm.provision "ansible_local" do |prov|
		prov.install = true
		prov.playbook = "/vagrant/ansible/playbook.yml"
		prov.verbose = true
  end
end
