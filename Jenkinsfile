pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {
                    echo "Testing the app... (e.g., running npm test)"
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo "Building the Docker Image locally on Jenkins..."
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    def dockerCmd = 'docker run -p 3000:3080 -d shahzadk1/make:v1'

                    sshagent(['ec2-server-key']) {
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@51.102.248.62 ${dockerCmd}"
                    }
                }
            }
        }
    }
}                   
