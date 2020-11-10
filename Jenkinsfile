pipeline {
    agent {
        docker { image 'yossie17/terratorm:v4'}
    }
    stages {
        stage('AWS-Credentials') {
            steps {
                sh 'hostname'
                sh 'mkdir /root/.aws/'
                sh 'envsubst  < credentials.template > /root/.aws/credentials'
            }
        }
        
        stage('Deploy EKS Cluster') {
            steps {
                sh 'terraform -v'
                sh 'terraform init terraform/'
                sh 'terraform plan terraform/'
                sh 'terraform apply -auto-approve terraform/'

            }
        }

        stage('Deploy exemple app') {
            steps {
                sh 'aws eks update-kubeconfig --eks-cluster --region eu-central-1'
                sh 'kubectl apply -f deployment.yml'

            }
        }
    }
}


