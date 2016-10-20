Some AWS related stuff.

# Requirements
## OS
### Cygwin
Assuming [apt-cyg](https://github.com/transcode-open/apt-cyg) installed.

    $ apt-cyg install gcc-core openssl-devel
    $ export CFLAGS="-D_DEFAULT_SOURCE"

### Ubuntu 14.04
    $ sudo apt-get update; sudo apt-get install -y libssl-dev python-pip
    
## Python
    $ pip install -r requirements.txt

## Environment
Configuration for AWS CLI:

    AWS_ACCESS_KEY_ID="KEY_ID_HERE"
    AWS_SECRET_ACCESS_KEY="ACCES_KEY_HERE"

Required for the AWS playbook:

    AWS_DEFAULT_REGION="us-east-1"
    AWS_DEFAULT_ZONES="b,d"
    AWS_DEFAULT_KEYPAIR="my_ssh_keypair_name"

# Aliases
Import aliases:

    $ . aliases.sh

# AMIs
Reference the [console's listing](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#LaunchInstanceWizard:) for some popular choices.

Also, there's [Ubutu's AMI locator page](https://cloud-images.ubuntu.com/locator/ec2/).

# Examples

Creating a VPC:

    $ ansible-playbook -e 'project=blog instance_type=m3.xlarge admin_user=tito github_user=belminf dns_zone=aws.example.com' playbooks/create_vpc.yaml
