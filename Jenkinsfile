pipeline {
    agent any

    environment {
        EC2_IP = '54.236.60.125'
    }

    stages {
        stage ('fetch') {
            steps {
                script {
                    echo "Pull Web Script from GitHub"
                    git branch: 'jenkins', url: 'https://github.com/seunayolu/jenkins_deploy_ec2.git'
                }
            }
        }

        stage ('deploy to EC2') {
            steps {
                script {
                    echo "deploying shell script to EC2"
                    def shellCmd = "bash ./websetup.sh"
                   sshagent(['jenkins-ec2']) {
                        sh "scp -o StrictHostKeyChecking=no websetup.sh ubuntu@$EC2_IP:/home/ubuntu"
                        sh "ssh -o StrictHostKeyChecking=no ubuntu@$EC2_IP ${shellCmd}"
                    }
                }
            }
        }
    }

}