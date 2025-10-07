pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo "Cloning code..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building JAR..."
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}

