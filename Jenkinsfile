pipeline {
    agent any

    stages {
        stage('Check Tools') {
            steps {
                sh 'echo "Java version:"'
                sh 'java -version'
                sh 'echo "Maven version:"'
                sh 'mvn -version'
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
