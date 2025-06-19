pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-app:latest .'
                echo 'Docker image built successfully!'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests (placeholder)'
                // Add real tests here if you expand the app
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop my-app || true'  // Stop if already running
                sh 'docker rm my-app || true'    // Remove if exists
                sh 'docker run -d --name my-app -p 80:3000 my-app:latest'
                echo 'App deployed on port 80!'
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed!'
        }
        success {
            echo 'CI/CD pipeline ran successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}
