# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "precise64"

  config.vm.forward_port 5000, 5000
  config.vm.forward_port 4567, 4567

  config.vm.provision :puppet, :options => ["--debug", "--verbose", "--summarize", "--reports", "store,riemann"] do |puppet|
    puppet.manifests_path = "manifests"
    puppet.module_path    = "modules"
    puppet.manifest_file  = "site.pp"
  end
end