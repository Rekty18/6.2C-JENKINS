pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                // Use Maven to build the code
                sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Use JUnit for unit tests
                sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                // Use SonarQube for code analysis
                sh 'mvn sonar:sonar'
            }
        }
        stage('Security Scan') {
            steps {
                // Use OWASP Dependency-Check for security scan
                sh 'dependency-check.sh'
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Deploy to AWS EC2 instance
                sh './deploy-to-staging.sh'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run Postman tests against staging environment
                sh 'newman run my_collection.json'
            }
        }
        stage('Deploy to Production') {
            steps {
                // Deploy to AWS EC2 instance
                sh './deploy-to-production.sh'
            }
        }
    }
    post {
        failure {
            // Send email notifications for failure
            mail to: 'hashen180@gmail.com', subject: 'Pipeline Failed', body: 'Check logs'
        }
        success {
            // Send email notifications for success
            mail to: 'hashen180@gmail.com', subject: 'Pipeline Succeeded', body: 'Check logs'
        }
    }
}
