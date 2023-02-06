pipeline {
    agent any
    parameters {
        booleanParam(name: 'Refresh',
                    defaultValue: false,
                    description: 'Read Jenkinsfile and exit.')
		    }
    stages {
        stage('update apt cache') {
            steps {
                sh 'sudo apt update'
            }
        }
        stage('install apache') {
            steps {
                sh 'sudo apt install apache2 -y'
            }
        }
        stage('SSH') {
            steps {
                sh '''
                   #!/bin/bash
                   ssh -i /home/jenkins/.ssh/training.pem -o StrictHostKeyChecking=no ubuntu@10.1.1.10 << EOF
                   sudo apt install nginx -y
                   touch readme
                   echo "Hello World - Success!" > readme
                   cat readme
                   << EOF
                '''
            }
        }
    }
}
