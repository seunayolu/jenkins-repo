pipeline {
    agent any

    environment {
        EC2_IP = '192.168.0.1'
    }

    stages {
        stage ('fetch') {
            steps {
                script {
                    echo "Create a folder"
                    sh "mkdir -p jenkins-class"
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