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
        
        stage('Test') {
            steps {
                sh 'terraform -v'
                sh 'terraform init terraform/'
                sh 'terraform plan terraform/'

            }
        }
    }
}


