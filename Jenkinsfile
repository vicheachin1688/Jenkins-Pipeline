pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the code!"
                echo "Tool: Maven"
                // Example command for Maven (not executed here)
                // sh 'mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Unit and integration testing!"
                echo "Tools: use JUnit or TestNG for unit tests"
                // Example command for unit and integration tests (not executed here)
                // sh 'mvn test'
            }
            post {
                success {
                    emailext to: "chinsovatanakvichea@gmail.com",
                        subject: "Unit and Integration Tests - SUCCESS",
                        body: "Unit and Integration Test was successful.",
                        attachLog: true
                }
                failure {
                    emailext to: "chinsovatanakvichea@gmail.com",
                        subject: "Unit and Integration Tests - FAILURE",
                        body: "Unit and Integration Test failed.",
                        attachLog: true
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Analyzing the code!"
                echo "Tool: ESLint"
                // Example command for ESLint (not executed here)
                // sh 'npx eslint . --ext .js,.ts'
            }
        }

        stage('Security Scan') {
            steps {
                echo "Scanning for potential security risks!"
                echo "Tool: Trivy"
                // Example command for Trivy (not executed here)
                // sh 'trivy fs .'
            }
            post {
                success {
                    emailext to: "chinsovatanakvichea@gmail.com",
                        subject: "Security Scan - SUCCESS",
                        body: "Security scan was successful.",
                        attachLog: true
                }
                failure {
                    emailext to: "chinsovatanakvichea@gmail.com",
                        subject: "Security Scan - FAILURE",
                        body: "Security scan failed.",
                        attachLog: true
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying to staging"
                echo "Tool: Custom deployment script"
                // Example command for deployment (not executed here)
                // sh 'deploy-script.sh staging'
            }
        }

        stage('Integration Test on Staging') {
            steps {
                echo "Integration testing on staging"
                echo "Tool: Custom integration test script"
                // Example command for integration testing (not executed here)
                // sh 'integration-tests.sh'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying to production"
                echo "Tool: Custom deployment script."
                // Example command for production deployment (not executed here)
                // sh 'deploy-script.sh production'
            }
        }
    }

    post {
        success {
            emailext to: "chinsovatanakvichea@gmail.com",
                subject: "Pipeline Success",
                body: "The pipeline has completed successfully.",
                attachLog: true
        }
        failure {
            emailext to: "chinsovatanakvichea@gmail.com",
                subject: "Pipeline Failure",
                body: "The pipeline has failed.",
                attachLog: true
        }
    }
}
