# Ansible_AWS_S3

1. Install AWS CLI
```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install

aws --version
```


2. Go to AWS Console -> IAM -> Access management - Users -> Create user -> Give name -> Attach Policies - AmazonEC2FullAccess -> Create user


3. In the AM -> Access management - Users -> Select the created user -> Security credentials -> Create access key -> Select Application running outside AWS -> Next -> Create access key -> Done 


4. Configure AWS CLI
```
aws configure
```
`Just give Access Key and Secret Key followed by ENTER-ENTER`

`REGION - us-west-1`


5. Install boto3

```
pip install boto3
```

6. Install Ansible & its AWS Collection
```
sudo apt install ansible -y
```
```
ansible-galaxy collection install amazon.aws
```

7. List the AWS buckets created with defaults
```
aws s3 ls
```
![image](https://github.com/user-attachments/assets/5841c16f-8b7c-4741-82d5-db85079b475c)

![image](https://github.com/user-attachments/assets/4af6af00-8e19-4e07-9f8b-59cc04ce4df4)


8. Execute the YAML to Enable Versioning on the AWS Buckets

