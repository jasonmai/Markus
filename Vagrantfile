# This Vagrantfile is for development use only.
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "markusproject/ubuntu"

  # Set this to your private key if you're having trouble
  # ssh-ing into Vagrant (it's requiring a password)
  config.ssh.private_key_path = "c:/Users/Jason Mai/.ssh/id_rsa"

  # Allow instance to see project folder.
  # Warning: This may cause problems with your Vagrant box!
  #          Enable at your own risk.
  # config.vm.synced_folder ".", "/home/vagrant/Markus"

  # Access the server running on port 3000 on the host on port 3000.
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  
  # Access to server through SSH from external machine on same network as host
  config.vm.network "forwarded_port", guest: 22, host: 2222, host_ip: "0.0.0.0",
                    id: "ssh", auto_correct: true

  config.vm.provider "virtualbox" do |vb|
    # Uncomment the following line if you want a GUI.
    # vb.gui = true
    vb.name = "markus"
    vb.memory = 2048
  end
end
