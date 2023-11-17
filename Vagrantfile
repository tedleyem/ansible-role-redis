Vagrant.configure("2") do |config|
# Defining a New VM named server and assign to a variable named dev
  config.vm.define "fedora" do |fedora|
    fedora.vm.hostname = "fedora-dev"
    fedora.vm.box = "generic/fedora37"
  end

  config.vm.define "debian" do |debian|
    debian.vm.hostname = "debian-dev"
    debian.vm.box = "debian/bookworm64"
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.hostname = "ubuntu-dev"
    ubuntu.vm.box = "ubuntu/focal64"
  end

  config.vm.define "arch" do |arch|
    arch.vm.hostname = "arch-dev"
    arch.vm.box = "archlinux/archlinux"
  end

  config.vm.define "rhel8" do |rhel|
    rhel.vm.hostname = "rhel-dev"
    rhel.vm.box = "generic/rhel8"
  end

  config.vm.define "rocky" do |rocky|
    rocky.vm.hostname = "rocky-dev"
    rocky.vm.box = "generic/rocky8"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.inventory_path = "tests/inventory.yml"
    ansible.playbook="playbook.yml"
    ansible.groups = {
      "group" => ["vagrant"],
  }
  end

end
