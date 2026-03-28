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
            withCredentials([file(credentialsId: 'ec2-pem-file', variable: 'KEY_FILE')]) {
                sh """
                ssh -i ${KEY_FILE} -o StrictHostKeyChecking=no ec2-user@51.102.248.62 "
                    docker stop \\\$(docker ps -q) || true && 
                    docker rm \\\$(docker ps -aq) || true && 
                    docker run -d -p 3000:3080 shahzadk1/make:v1
                "
                """
            }
        }
    }
}
    }
}                   
