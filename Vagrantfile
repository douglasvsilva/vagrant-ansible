Vagrant.configure("2") do |config|
  config.vm.define "vm1" do |vm1|
    vm1.vm.box = "ubuntu/bionic64"
    vm1.vm.network "private_network", ip: "192.168.50.4"
  end

  config.vm.define "vm2" do |vm2|
    vm2.vm.box = "ubuntu/bionic64"
    vm2.vm.network "private_network", ip: "192.168.50.5"
  end
end
