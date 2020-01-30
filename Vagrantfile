Vagrant.configure("2") do |config|
  config.vm.define "artifactory.example.com" do |node1|
    node1.vm.box = "centos/7"
    node1.vm.synced_folder '.', '/vagrant', disabled: true
    node1.vm.network "forwarded_port", guest: 443, host: 1443, host_ip: "0.0.0.0"
    node1.vm.provider :libvirt do |domain|
        domain.memory = 1024
        domain.cpus = 2
    end
  end
  config.vm.define "jenkins.example.com" do |node2|
    node2.vm.box = "centos/7"
    node2.vm.synced_folder '.', '/vagrant', disabled: true
    node2.vm.network "forwarded_port", guest: 443, host: 2443, host_ip: "0.0.0.0
"
    node2.vm.provider :libvirt do |domain|
        domain.memory = 1024
        domain.cpus = 2
    end
  end
  config.vm.define "mediawiki.example.com" do |node3|
    node3.vm.box = "centos/7"
    node3.vm.synced_folder '.', '/vagrant', disabled: true
    node3.vm.network "forwarded_port", guest: 443, host: 3443, host_ip: "0.0.0.0
"
    node3.vm.provider :libvirt do |domain|
        domain.memory = 1024
        domain.cpus = 2
    end
  end
  config.vm.define "subversion.example.com" do |node4|
    node4.vm.box = "centos/7"
    node4.vm.synced_folder '.', '/vagrant', disabled: true
    node4.vm.provider :libvirt do |domain|
        domain.memory = 512
        domain.cpus = 2
    end
  end
  config.vm.define "zabbix.example.com" do |node5|
    node5.vm.box = "centos/7"
    node5.vm.synced_folder '.', '/vagrant', disabled: true
    node5.vm.network "forwarded_port", guest: 443, host: 5443, host_ip: "0.0.0.0
"
    node5.vm.provider :libvirt do |domain|
        domain.memory = 1024
        domain.cpus = 2
    end
  end
  config.vm.define "management.example.com" do |node6|
    node6.vm.box = "centos/7"
    node6.vm.synced_folder '.', '/vagrant', disabled: true
    node6.vm.network "forwarded_port", guest: 110, host: 6110, host_ip: "0.0.0.0
"
    node6.vm.provider :libvirt do |domain|
        domain.memory = 2048
        domain.cpus = 2
    end
  end
end
