pipeline {
    agent any
    tools { maven 'Maven-3.8.6' }  
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/calculator.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
    }
}
// Webhook test
