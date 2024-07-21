# Ansible_AWS_S3_PaC

## Policy as Code

Policy as Code (PaC) in DevSecOps refers to the practice of defining and managing security policies through code. This approach enables automated, consistent, and scalable enforcement of security controls and compliance requirements across the software development lifecycle. 

### Key Concepts of Policy as Code:

#### Codification of Policies-
Security policies, compliance requirements, and governance rules are written in code, similar to how infrastructure is defined in Infrastructure as Code (IaC).
Policies are typically defined using declarative languages or scripts.

#### Automation-
Policies are automatically enforced through CI/CD pipelines.
Tools continuously monitor and ensure compliance with the defined policies.

#### Version Control-
Policies as code are stored in version control systems (e.g., Git), allowing for versioning, auditing, and change tracking.
This ensures that any changes to policies are transparent and traceable.

#### Integration with DevOps Tools
PaC integrates with DevOps tools and platforms, enabling seamless policy enforcement across development, testing, and production environments.
Common integrations include CI/CD tools, configuration management tools, and cloud management platforms.

### Benefits of Policy as Code:

#### Consistency and Accuracy-
Policies are applied consistently across environments, reducing the risk of human error.
Automated checks and enforcement ensure that policies are adhered to accurately.

#### Scalability-
PaC enables scalable policy enforcement across multiple environments and numerous resources.
It supports the rapid deployment and scaling of applications while maintaining compliance.

#### Auditability and Transparency-
Policies as code provide an auditable trail of policy definitions and changes.
This transparency is crucial for compliance and regulatory requirements.

#### Shift-Left Security-
By integrating security policies early in the development process, PaC promotes the shift-left security approach.
It helps identify and remediate security issues early, reducing the cost and impact of security vulnerabilities.

### Example Use Cases:

#### Infrastructure Security-
Ensure that cloud resources (e.g., AWS S3 buckets, IAM roles) comply with security best practices.
Automatically remediate non-compliant resources.

#### Application Security-
Enforce secure coding practices and compliance checks during the build and deployment stages.
Prevent deployment of applications with known vulnerabilities.

#### Compliance and Governance-
Implement regulatory compliance requirements (e.g., GDPR, HIPAA) as code.
Continuously monitor and enforce compliance across the organization.

----

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

Before executing to check the Versioning on the AWS portal for `test1-pavan-raj` bucket

![image](https://github.com/user-attachments/assets/7f586a70-8aa5-4ab2-9639-d029dcfdacd6)

```
ansible-playbook s3_versioning.yaml
```
After executing to check the Versioning on the AWS portal for `test1-pavan-raj` bucket and for other buckets as well which is enabled 

![image](https://github.com/user-attachments/assets/76b479cd-cbfb-4114-aa57-d522fcc43273)
