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
                    ssh -i /home/jenkins/.ssh/training.pem ubuntu@18.169.167.8
                    touch /home/ubuntu/readme
                    echo "Hello World" > /home/ubuntu/readme
                '''
            }
        }
    }
}
