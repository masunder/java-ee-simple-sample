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
                withMaven(maven: 'mvn', jdk: 'openjdk-11') {
                    sh 'mvn test'
                }
            }
        }
        stage('Deploy') {
            steps {
                withMaven(maven: 'mvn', jdk: 'openjdk-11') {
                    mvn 'mvn install'
                }
            }
        }
    }
}
