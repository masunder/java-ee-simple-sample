pipeline {
    agent any
    stages {
        stage('Init') {            
            stage('Test') {
                IMAGE = readMavenPom().getArtifactId()
                VERSION = readMavenPom().getVersion()
                echo "IMAGE: ${IMAGE}"
                echo "VERSION: ${VERSION}"
              }
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
        stage('Publish') {
            steps {
                withMaven(maven: 'mvn') {
                    sh "mvn deploy"
                }
            }
        }
        stage('Depoy') {
            steps {
                echo "Here is the deploy step"
            }
        }
    }
}
