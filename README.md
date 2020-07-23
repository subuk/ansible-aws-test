# Ansible ec2 modules test

Naive ec2 configuration with ansible.

## How to use

Install dependencies:

    python3 -m venv ~/ansible-aws-test
    . ~/ansible-aws-test/bin/activate
    pip install -r requirements.txt

Configure AWS [credentials](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) as usual.

Configure `ec2_key_name`, `ec2_subnets`, `ec2_vpc_id` in `inventory/group_vars/all.yml` (or create myvars.yml file and pass it to ansible as `-e @myvars.yml`).

Check AWS filters in `inventory/aws_ec2.yml`.

Check security groups CIDR in `inventory/group_vars/all.yml`

Enable VPN for VPC private addresses.

Run:

    ansible-playbook site.yml -u centos -b
