pipeline {
    agent any

    tools {
        maven 'Maven 3.9.6'
        jdk 'jdk21'
    }

    stages {
        stage('Check Tools') {
            steps {
                bat 'echo Checking Java and Maven versions...'
                bat 'java -version'
                bat 'mvn -version'
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/trishaboda/devopsmavenapp.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/devopsmavenapp-1.0-SNAPSHOT.jar', fingerprint: true
            }
        }
    }
}
