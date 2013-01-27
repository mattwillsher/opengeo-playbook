require 'vagrant-ansible'

Vagrant::Config.run do |config|
  config.vm.box     = "precise32_cloudimage"
  config.vm.box_url = "http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-vagrant-i386-disk1.box"
  
  config.vm.customize ["modifyvm", :id, "--memory", "512"]

  config.vm.host_name = "opengeo"
  config.vm.network :hostonly, "192.168.241.10"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "opengeo-ubuntu.yml"
    ansible.hosts = "opengeo-server"
  end
end
