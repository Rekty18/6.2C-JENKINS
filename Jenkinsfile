pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Echo the tool being used for building
                echo 'Using Maven for building the project.'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                // Echo the tools being used for testing
                echo 'Using JUnit for unit tests and TestNG for integration tests.'
            }
            post {
                always {
                    // Send email notification using built-in mail step
                    mail to: 'hashen180@gmail.com',
                         subject: "Jenkins Build: ${currentBuild.fullDisplayName}",
                         body: "Unit and Integration Tests ${currentBuild.result}: ${env.BUILD_URL}"
                }
            }
        }

        stage('Code Analysis') {
            steps {
                // Echo the tool being used for code analysis
                echo 'Using SonarQube for code analysis.'
            }
        }

        stage('Security Scan') {
            steps {
                // Echo the tool being used for security scan
                echo 'Using OWASP Dependency-Check for security scan.'
            }
            post {
                always {
                    // Send email notification using built-in mail step
                    mail to: 'hashen180@gmail.com',
                         subject: "Jenkins Build: ${currentBuild.fullDisplayName}",
                         body: "Security Scan ${currentBuild.result}: ${env.BUILD_URL}"
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                // Echo the tool being used for deployment to staging
                echo 'Using AWS Elastic Beanstalk for deployment to staging environment.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                // Echo the tool being used for integration tests on staging
                echo 'Using Selenium for running integration tests on staging environment.'
            }
        }

        stage('Deploy to Production') {
            steps {
                // Echo the tool being used for deployment to production
                echo 'Using AWS Elastic Beanstalk for deployment to production environment.'
            }
        }
    }

    post {
        always {
            // Echo that the pipeline has finished executing
            echo 'Pipeline has finished executing.'
        }
    }
}
//commit
