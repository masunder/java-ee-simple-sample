pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withMaven(globalMavenSettingsConfig: 'maven-global', maven: 'Maven 3.8.1') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(globalMavenSettingsConfig: 'maven-global', maven: 'Maven 3.8.1') {
                    sh 'mvn test'
                }
            }
        }
        stage('Deploy') {
            steps {
                withMaven(globalMavenSettingsConfig: 'maven-global', maven: 'Maven 3.8.1') {
                    mvn 'mvn install'
                }                
            }
        }
    }
}
