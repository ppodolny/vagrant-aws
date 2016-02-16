# vagrant-aws
Vagrant based development environment for testing Ansible playbooks on top of AWS EC2.
Tested on Vagrant 1.8.x

Set your env. vars:
```
export AWS_DEFAULT_REGION=us-east-1
export AWS_SECRET_ACCESS_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
export AWS_ACCESS_KEY_ID=xxxxxxxxxxxxxx
export AWS_KEYPAIR_NAME=my-key
export AWS_SSH_KEY=~/.ssh/my-key.pem
export AWS_ACCESS_KEY=${AWS_ACCESS_KEY_ID}
export AWS_SECRET_KEY=${AWS_SECRET_ACCESS_KEY}

```

Install Vagrant plugin for AWS, add dummy box & launch Vagrant:
```
$ vagrant plugin install vagrant-aws
$ vagrant box add dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box
$ vagrant up --provider=aws
```
