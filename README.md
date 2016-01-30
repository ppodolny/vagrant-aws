# vagrant-aws
Vagrant based development environment for testing Ansible playbooks on top of AWS.

Set your env. vars:
```
export AWS_DEFAULT_REGION=us-east-1
export AWS_SECRET_ACCESS_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
export AWS_ACCESS_KEY_ID=xxxxxxxxxxxxxx
export AWS_KEYPAIR_NAME=my-key
export AWS_SSH_KEY=~/.ssh/my-key.pem
export AWS_ACCESS_KEY=${AWS_ACCESS_KEY_ID}
export  AWS_SECRET_KEY=${AWS_SECRET_ACCESS_KEY}

```

Install Vagrant plugin for AWS + launch vagrant:
```
vagrant plugin install vagrant-aws
vagrant up --provider=aws
```
