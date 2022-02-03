**Amazon EKS Cluster Creation**
This repository contains the following files:

eks-cluster.yaml: a CloudFormation template that defines an EKS cluster, including a VPC, the EKS control plane (master nodes) and the EKS worker nodes.
script.sh: a Bash script that applies the CloudFormation template to your AWS account and finalises the cluster creation, including kubectl configuration.

**Prerequisites**
Install the AWS CLI:
pip install awscli
Install the AWS IAM Authenticator:
go get -u -v github.com/kubernetes-sigs/aws-iam-authenticator/cmd/aws-iam-authenticator
Install kubectl:
brew install kubernetes-cli


**Run**
Edit parameters in script.sh:

NUM_WORKER_NODES: number of worker nodes for your EKS cluster
WORKER_NODES_INSTANCE_TYPE: EC2 instance type for the worker nodes
STACK_NAME: name of the CloudFormation stack for your EKS cluster
KEY_PAIR_NAME: name of an existing EC2 key pair for connecting to the worker nodes with SSH


**Run:**

./script.sh


**Note**
Any arguments that you pass to script.sh will be forwarded to the AWS CLI commands within the script. Thus, it is possible to specify an explicit region fo the cluster as follows:

./script.sh --region eu-west-1
