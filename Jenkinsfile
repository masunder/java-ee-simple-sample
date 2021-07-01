pipeline {
    agent any
    stages {
        stage('Init') {
            steps {
                withMaven(maven: 'mvn') {
                    sh "mvn -version"
                }
            }
        }
        stage('Build') {
            steps {
                withMaven(maven: 'mvn') {
                    sh "mvn clean compile"
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(maven: 'mvn') {
                    sh "mvn test"
                }
            }
        }
        stage('Deploy') {
            steps {
                withMaven(maven: 'mvn') {
                    sh "mvn install"
                }
            }
        }
    }
}
