pipeline {
    agent any
    tools {
        maven 'Maven 3.8.1'
        jdk 'openjdk-8'
    }
    stages {
        stage('Build') {
            steps {
                sh "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                mvn 'mvn install'
            }
        }
    }
}
