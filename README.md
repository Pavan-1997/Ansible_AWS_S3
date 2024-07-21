# Ansible_AWS_S3

1. Install AWS CLI
```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install

aws --version
```

2. Configure AWS CLI
```
aws configure
```
`Just give Access Key and Secret Key followed by ENTER-ENTER`

`REGION - us-west-1`


3. Install boto3

```
pip install boto3
```

4. Install Ansible & its AWS Collection
```
sudo apt install ansible -y
```
```
ansible-galaxy collection install amazon.aws
```

