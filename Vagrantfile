# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/focal64"

  config.vm.provision :ansible do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "site.yml"
    ansible.groups = {
      "observium" => ["default"],
      "observium:vars" => {
        "observium_domain" => "localhost",
        "observium_protocol" => "http",
        "observium_port" => 8080
      }
    }
    ansible.extra_vars = {
      "ansible_python_interpreter" => "/usr/bin/python3"
    }
  end

  config.vm.network "forwarded_port", guest: 80, host: 8080

end
