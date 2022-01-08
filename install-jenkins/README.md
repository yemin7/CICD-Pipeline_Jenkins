## Add aws profile name in dynamic inventory 'aws_ec2.yaml'

```
plugin: amazon.aws.aws_ec2
regions:
  - ap-southeast-1
boto_profile: <aws_profile>
```

## Add ec2 key pair path
``private_key_file=``

## Run Playbook
ansible-playbook main.yaml
