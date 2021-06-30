pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withMaven(maven: 'mvn', jdk: 'openjdk-11') {
                    sh "mvn clean compile"
                }
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
