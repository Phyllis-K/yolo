Vagrant.configure("2") do |config|
    # Use Ubuntu as the base box
    config.vm.box = "ubuntu/jammy64"  # You can use any other Ubuntu version like "ubuntu/focal64" or "ubuntu/jammy64"
  
    # Configure network settings (optional)
    config.vm.network "private_network", type: "dhcp"
  
    # Configure virtual machine (optional)
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "2024"  # Allocate 1GB of RAM to the VM
      vb.cpus = 2         # Allocate 2 CPUs to the VM
    end
  
    # Use Ansible as the local provisioner
    config.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yaml"  # Path to your Ansible playbook (you'll create this later)
    end
  end
  