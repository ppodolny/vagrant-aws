# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "dummy"
  config.vm.provider :aws do |aws, override|
    aws.access_key_id = ENV['AWS_ACCESS_KEY']
    aws.secret_access_key = ENV['AWS_SECRET_KEY']
    aws.region = ENV['AWS_DEFAULT_REGION'] 
    aws.keypair_name = ENV['AWS_KEYPAIR_NAME']
    override.ssh.private_key_path = ENV['AWS_SSH_KEY']
    override.ssh.username = "ubuntu"
    aws.ami = "ami-d05e75b8"
    aws.terminate_on_shutdown  = false
    aws.tags = {
      "Name"        => "vagrant-aws"
    }
    aws.user_data = <<-USER_DATA
    #!/bin/sh
    echo "Defaults    !requiretty" > /etc/sudoers.d/vagrant-init
    chmod 440 /etc/sudoers.d/vagrant-init
    USER_DATA
  end  
  config.vm.provision :ansible do |ansible|
     ansible.playbook = "playbook.yml"
     ansible.verbose = "v"
     ansible.host_key_checking = false
     ansible.sudo = true
   end
end
