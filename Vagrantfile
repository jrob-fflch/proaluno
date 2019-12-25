VAGRANTFILE_API_VERSION = "2"
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'libvirt'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.define :"samba" do |host|
      host.vm.box = "generic/ubuntu1804"
      host.vm.network :private_network, ip: "10.20.30.5"
      host.ssh.insert_key = false # important

      host.vm.provider :libvirt do |v|
        v.memory = 1024
        v.cpus = 1
      end
    end

    config.vm.define :"vm" do |host|
      host.vm.box = "generic/debian10"
      host.vm.network :private_network, ip: "10.20.30.6"
      host.ssh.insert_key = false # important

      host.vm.provider :libvirt do |v|
        v.memory = 1024
        v.cpus = 1
      end
    end

end
