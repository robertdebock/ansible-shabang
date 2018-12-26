Vagrant.configure("2") do |config|
  config.vm.define "node1.example.com" do |node1|
    node1.vm.box = "centos/7"
    node1.vm.synced_folder '.', '/vagrant', disabled: true
    node1.vm.provider :libvirt do |domain|
        domain.memory = 2048
        domain.cpus = 2
    end
  end
  config.vm.define "node2.example.com" do |node2|
    node2.vm.box = "centos/7"
    node2.vm.synced_folder '.', '/vagrant', disabled: true
    node2.vm.provider :libvirt do |domain|
        domain.memory = 2048
        domain.cpus = 2
    end
  end
  config.vm.define "node3.example.com" do |node3|
    node3.vm.box = "centos/7"
    node3.vm.synced_folder '.', '/vagrant', disabled: true
    node3.vm.provider :libvirt do |domain|
        domain.memory = 2048
        domain.cpus = 2
    end
  end
end
