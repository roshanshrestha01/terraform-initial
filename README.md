# Build

Project utilizes [registry](https://registry.terraform.io/) modules to build infrastructure

Register project modules

* [AWS VPC](https://github.com/terraform-aws-modules/terraform-aws-vpc)
* [AWS RDS AURORA](https://github.com/terraform-aws-modules/terraform-aws-rds-aurora)
* [AWS EC2](https://github.com/terraform-aws-modules/terraform-aws-ec2-instance)


> :warning: **Terraform state is not shared. So each initialize might create resource among team members**


## Install terraform

* Download terraform from [here](https://www.terraform.io/downloads.html).
* Unzip downloaded file
* Move unzip file `sudo mv terraform /usr/local/bin/`

## Service to setup from AWS dashboard
Services is to be created from AWS dashboard and configured in `main.ts`
* Create a `IAM` role
* Create a `Key Pair` 
* Ensure `SSL Certificate` 


## Setting aws credentials

```sh
$ export AWS_ACCESS_KEY_ID="<ACCESS_KEY_ID>"
$ export AWS_SECRET_ACCESS_KEY="<SECRET_ACCESS_KEY>"
$ export AWS_DEFAULT_REGION="<DEFAULT_REGION>"
```

## Terraform

```sh
$ terraform init
$ terraform plan
$ terraform apply
```

## Checklist
### Necessary packeges
- [ ] Execute `install.sh`to install necessary package and ruby 

### SSH hardening
- [ ] Change default ports also security group ports
- [ ] Enable Verbose Logging `LogLevel VERBOSE`
- [ ] Disable root access `PermitRootLogin no`
- [ ] Disconnet Idle session `ClientAliveInterval 300  ClientAliveCountMax 0`
- [ ] Disable Password Authentication `PasswordAuthentication no`

### OS hardening

- [ ] Delete unwanted users `deluser --remove-home <username>`
- [ ] Remove unwanted packages `apt autoremove --purge`

### Code base
- [ ] Configure `ssh-kekgen` in new user created
- [ ] Add public key of users in `.ssh/authrozied_keys`
- [ ] Clone projecs repo to server  