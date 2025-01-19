# eks_cluster

This repository provides resources for creating an Amazon Elastic Kubernetes Service (EKS) cluster using Terraform.

## Pre-requisites

Before you begin, make sure you have the following installed:

- **AWS CLI**: [Installation Guide](https://aws.amazon.com/cli/)
- **Terraform**: [Installation Guide](https://www.terraform.io/downloads.html)
- **VS Code with Terraform Extension**: [VS Code](https://code.visualstudio.com/) + [Terraform Extension](https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform)

## Creation

This project uses Terraform modules for creating the following AWS resources:

- **VPC**: Virtual Private Cloud for networking.
- **EKS Cluster**: Amazon Elastic Kubernetes Service for orchestrating containers.
  
The Terraform configuration defines variables for the modules and ensures a secure and scalable environment.

Additionally, **Security Groups** have been created to control access to the resources within the cluster.

versions.tf file will help to download latest versions of modules in which we will mention the versions for the modules. 
## Setup

1. Clone the repository:  
   `git clone https://github.com/mohammadsyed397/eks_cluster.git`

2. Configure AWS CLI:  
   `aws configure`
   it will ask for access id and secret key of your aws account 

4. Initialize Terraform:  
   `terraform init`

5. Apply Terraform configuration to create the EKS cluster:
   `terraform apply`
6. To integrate eks cluster with kubectl :
   `aws eks --region <your-region> update-kubeconfig --name <your-cluster-name>`
To view the resources and perform actions on nodes we need to create access entries based on your requirements
 

8. Verify the EKS cluster:  
   `kubectl get nodes`

9. Deploy applications to the EKS cluster:  
   `kubectl apply -f deployment.yaml`


## Cleanup

To destroy the created resources:  
`terraform destroy`

