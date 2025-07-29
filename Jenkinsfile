pipeline {
    agent any

    tools {
        maven 'Maven 3.9.6'  // Make sure this matches the name in Jenkins Global Tools
        jdk 'jdk21'        // Same for this — must match your configured JDK in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/trishaboda/devopsmavenapp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/devopsmavenapp-1.0-SNAPSHOT/*.jar', fingerprint: true
            }
        }
    }
}