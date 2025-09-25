# CICD

## Create infra using Jenkins
* First create pipelines of 00-vpc
    - Create ROBOSHOP Folder in jenkins 
    - Then Create New Item 00-vpc
    - Configure 00-vpc -> pipeline Script from SCM Git add <Git-repo-URL> 
    - Branch Specific -> */main
    - Script Path -> 00-vpc/Jenkinsfile
* Same Like VPC we can create for other components also (SG, BASTION, ACM, EKS and ALB)
* Once we creating all pipeline just you to build now for 00-VPC, it will automatically Trigger remaining components because we wrote a Jenkinsfile is to Trigger automatically all components in Parallel and Sequential

## EKS Setup
* Create Namespaces
* Create Cluster
```
aws eks update-kubeconfig --region us-east-1 --name roboshop-dev
```
* Add jenkins security group in EKS Control plane security group to allow Jenkins port no is 443 HTTPS