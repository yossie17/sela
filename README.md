# sela

to comlete the task i chese to use Terraform and Jenkins over AWS to deploy 
a EKS cluster and ECR:

all the terraform code is in the folder terraform 

i used a jenkins server (deploying with docker, docker dind) to run the deploying job (i use a coustme terraform-aws image as a docker agent) 
the docker files for the jenkins and aws-terraform attached and also the jenkins file  

