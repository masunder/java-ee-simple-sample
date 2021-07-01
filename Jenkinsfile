pipeline {
    agent any
    stages {
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
