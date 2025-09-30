pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            // write your logic here
           git 'https://github.com/expertszen/java-standalone-application.git'
        }
        stage('Build') {
            // write your logic here
            sh 'mvn clean package'
        }
        stage('Run Application') {
            // write your logic here
            sh 'mvn test'
        }
        stage('Test') {
            // write your logic here
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
                success {
            echo 'Pipeline successfully completed!'
        }
        failure {
            echo 'Pipeline failed. Check the logs.'
        }
            }
        }
    }
}
