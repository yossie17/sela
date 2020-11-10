# sela

To complete the task i chose to use Terraform and Jenkins over AWS to deploy
an AKS cluster and ECS:

all the terraform code is in the folder terraform.

I used Jenkins server (deploying with Docker, docker dind). to run the deployment job (i used a custom terraform-aws image as a docker agent).




