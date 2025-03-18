pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Starting Build...'
                sh 'g++ -o PES1UG22CS463 PES1UG22CS463-1.cpp'
                echo 'Build Completed Successfully'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh './PES1UG22CS463'
                echo 'Tests Completed Successfully'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
        
                echo 'Deployment Successful'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs for details.'
        }
        always {
            echo 'Pipeline execution completed, check results above.'
        }
    }
}
