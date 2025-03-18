pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Starting Build...'
                sh 'mvn clean install'
                echo 'Build Completed Successfully'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh 'mvn test'
                echo 'Tests Completed Successfully'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
                sh 'mvn deploy'
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
