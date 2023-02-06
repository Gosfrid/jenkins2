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
                    ssh -o StrictHostKeyChecking=no -i /home/jenkins/.ssh/training.pem ubuntu@10.1.1.10
                    touch /home/ubuntu/readme
                    echo "Hello World" > /home/ubuntu/readme
                '''
            }
        }
    }
}
