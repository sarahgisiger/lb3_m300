Vagrant.configure(2) do |config|
	config.vm.box = "hashicorp/bionic64"

	#hier werden div. VM Konfigurationen definiert
	config.vm.provider "virtualbox" do |vb|
		vb.memory = "1024" 
		vb.name = "M300_LB3"
		vb.cpus = 2  
	end
	
	#hier wird ein privates Netzwerk erstellt + der Hostname wird gesetzt
	config.vm.hostname = "LB3"
	config.vm.network "private_network", ip:"192.168.60.20"
  
	#hier wird der synchronisierter Folder angegeben.
	config.vm.synced_folder ".", "/home/vagrant"
	
	#Installiert Docker & Docker Compose + startet gleich das docker-compose.yml File
	config.vm.provision :docker
	config.vm.provision :docker_compose , yml: "/home/vagrant/docker-compose.yml", run: "always"
end