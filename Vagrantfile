# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"

  config.vm.provision :ansible do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "site.yml"
    ansible.groups = {
      "observium" => ["default"],
      "observium:vars" => {
        "observium_protocol" => "http"
      }
    }
    ansible.extra_vars = {
      "ansible_python_interpreter" => "/usr/bin/python3"
    }
  end

end
