pipeline {
    agent any
    stages {
        stage('Init') {
            steps {
                withMaven(maven: 'mvn', jdk: 'jdk-16') {
                    sh "mvn -version"
                }
            }
        }
        stage('Build') {
            steps {
                withMaven(maven: 'mvn', jdk: 'jdk-16') {
                    sh "mvn clean compile"
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(maven: 'mvn', jdk: 'jdk-16') {
                    sh "mvn test"
                }
            }
        }
        stage('Deploy') {
            steps {
                withMaven(maven: 'mvn', jdk: 'jdk-16') {
                    sh "mvn install"
                }
            }
        }
    }
}
