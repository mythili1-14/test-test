pipeline {
    agent any
    
    environment {
        DOCKERHUB_USERNAME = 'mythili121'
        DOCKERHUB_CREDENTIAL_ID = 'dockerhub-cred'
        AWS_SSH_CREDENTIAL_ID = 'aws-ec2-key'
        EC2_IP = '54.172.118.89'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: "https://github.com/mythili1-14/devops-build.git", credentialsId: 'github-cred', branch: "${env.BRANCH_NAME}"
            }
        }

        stage('Build and Push') {
            steps {
                withCredentials([usernamePassword(credentialsId: DOCKERHUB_CREDENTIAL_ID, usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    sh "echo \$DOCKER_PASSWORD | docker login -u \$DOCKER_USERNAME --password-stdin"
                }
                sh "./build.sh"
            }
        }
        
        stage('Deploy to Server') {
            steps {
                sshagent(credentials: [AWS_SSH_CREDENTIAL_ID]) {
                    sh "scp -o StrictHostKeyChecking=no deploy.sh ubuntu@${EC2_IP}:/tmp/deploy.sh"
                    sh "ssh -o StrictHostKeyChecking=no ubuntu@${EC2_IP} /tmp/deploy.sh ${env.BRANCH_NAME == 'main' ? 'prod main' : 'dev dev'}"
                }
            }
        }
    }
}
