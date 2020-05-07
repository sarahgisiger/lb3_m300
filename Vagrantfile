Vagrant.configure(2) do |config|
	config.vm.box = "ubuntu/xenial64"

  #Hier werden die Port Weiterleitungen definiert
  #Webserver
  config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  #MySQL
  config.vm.network "forwarded_port", guest:3306, host:3306, auto_correct: true 

	
  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.hostname = "LB3"
  config.vm.network "private_network", ip:"192.168.60.18"
	
	config.vm.synced_folder ".", "/home/vagrant"
	
	
	#hier werden div. VM Konfigurationen eingestellt
	config.vm.provider "virtualbox" do |vb|
		vb.memory = "1024" 
		vb.name = "M300_LB3"
		vb.cpus = 2  
	end
	
	#Installiert Docker & Docker Compose + startet gleich das docker-compose.yml File
	config.vm.provision :docker
	config.vm.provision :docker_compose , yml: "/home/vagrant/docker-compose.yml", run: "always"
end
