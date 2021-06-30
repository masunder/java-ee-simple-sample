pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withMaven(maven: 'mvn', jdk: 'openjdk-8') {
                    sh "mvn clean compile"
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(maven: 'mvn', jdk: 'openjdk-8') {
                    sh 'mvn test'
                }
            }
        }
        stage('Deploy') {
            steps {
                withMaven(maven: 'mvn', jdk: 'openjdk-8') {
                    mvn 'mvn install'
                }
            }
        }
    }
}
