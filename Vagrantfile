# -â€‹*- mode: ruby -*â€‹-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

 config.vm.define "default"

 config.vm.box = "debian/jessie64"

 config.vm.hostname = "vagrant-exakat"

 config.vm.provider :virtualbox do |vb|
   vb.gui = false
   vb.customize ["modifyvm", :id, "--memory", "4096", "--cpus", "4"]
 end

 config.vm.provision :ansible do |ansible|
   ansible.verbose = "vvvv"
   ansible.raw_arguments = ['--timeout=300']
   ansible.sudo = true
   ansible.playbook = ".ansible/exakat.yml"
 end
end
