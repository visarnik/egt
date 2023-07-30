

### Pre-reqs
This demo is configured to run on Amazon EKS, so you will need the following:
  - Terraform required_version = ">= 1.4.0"
  - AWS cli v2
  - kubectl v1.27.4
  - Helm v3.12.2

#### Build the code
Builds are triggered automatically on push with github actions and docker images are pushed to DockerHub repository.
#### Build the hosting infrastructure
Go to Terraform folder and run the following commands:
 ```bash
terraform init
terraform plan – to check what will be created
terraform apply – to apply the configuration on AWS
```
#### Deploy application
 ```bash
helm install --dry-run release-1.0.0 egt-demo – to test configuration
helm install  release-1.0.0 egt-demo – to install the configuration.
```
You can acces app on
 ```bash
http://a79d5ff4d736e4ad8bc0fc5c3f76e1ac-274027343.ap-northeast-2.elb.amazonaws.com:3000
```
