required_version ">= 1.8.0"
# Defining a New VM named server and assign to a variable named dev
config.vm.define "virtualbox" do |dev| 
    # Set the hostname of the VM 
    dev.vm.hostname = "devbox-ansible"
     
    # Set the box (OS) for the Virtual machine, we use centos7 
    dev.vm.box = "geerlingguy/ubuntu2004" 
    
    dev.vm.memory = "2048"
    # Port forwarding configuration as per our requirement 
    #dev.vm.network "forwarded_port", guest: "80", host: "8080" 
    
    # Creating a Shared Directory between host and guest VM 
    #dev.vm.synced_folder "/apps/shared", "/shared" 
    
    # Provision the webserver with Ansible, Execute the playbook 
    dev.vm.provision "ansible" do |ansible| 
    ansible.verbose = "v"
    # Mention the fully qualified path and name of playbook. 
    # If no path mentioned, vagrant will take the base directory where Vagrantfile resides  
    ansible.playbook="playbook.yaml" 
    end 
end
