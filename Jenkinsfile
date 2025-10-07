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
                echo "Building WAR..."
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                echo "Archiving WAR..."
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }
    }
}
