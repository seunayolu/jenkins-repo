pipeline {
    agent any

    environment {
        EC2_IP = '192.168.0.1'
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

        stage ('build') {
            steps {
                script {
                    echo "Build my app"
                }
            }
        }
    }

}