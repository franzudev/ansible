

Vagrant.configure("2") do |config|
  config.vm.provider :virtualbox

  config.vm.define "ansible-target1" do |machine|
    machine.vm.box = "centos/8"
    machine.vm.network "private_network", ip: "192.168.56.21"
    machine.vm.disk :disk, size: "40GB", name: "extra_storage1"
  end

  config.vm.define "ansible-target2" do |machine|
    machine.vm.box = "centos/8"
    machine.vm.network "private_network", ip: "192.168.56.22"
    config.vm.disk :disk, size: "40GB", name: "extra_storage2"
  end

  config.vm.define 'controller' do |machine|
    machine.vm.box = "arabadj/centos8-powerbox"
    machine.vm.network "private_network", ip: "192.168.56.11"

    machine.vm.provision :ansible_local do |ansible|
      ansible.playbook       = "site.yaml"
      ansible.verbose        = true
      ansible.install_mode = "pip"
      ansible.install        = true
      ansible.limit          = "all"
      ansible.inventory_path = "inventory"
    end
  end

end
