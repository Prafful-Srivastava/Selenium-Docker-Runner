pipeline {
    agent any
    stages {
        stage("Start Grid") {
            steps {
                bat 'docker-compose up -d hub chrome firefox'
            }
        }
        stage("Run Tests") {
            steps {
                bat 'docker-compose up search-module book-flight-module'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'output/**'
        }
        success {
            script {
                bat 'docker-compose down'
            }
        }
        failure {
            script {
                bat 'docker-compose down'
            }
        }
    }
}