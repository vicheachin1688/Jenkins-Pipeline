pipeline {
    agent any
    }
    stages {
        stage('Build') {
            steps {
                echo "Building the code!"
                echo "Tool: Maven"
                // Example command for Maven (not executed here)
                // Use Maven to clean previous builds and compile the code, then package it into a deployable format (e.g., .jar or .war)
                // sh 'mvn clean package'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Unit and integration testing!"
                echo "Tools: use JUnit or TestNG for unit test"
                // Example commands (not executed here)
                // sh 'mvn test'
            }
            post {
                success {
                    mail to: "konellyskaishann@gmail.com",
                        subject: "Unit and Integration Tests",
                        body: "Unit and Integration Test successful."
                }
                failure{
                    mail to: "konellyskaishann@gmail.com",
                        subject: "Unit and Integration Tests",
                        body: "Unit and Integration Test failed"
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo "Analyzing the code!"
                echo "Tool: ESLint"
                // Example command for SonarQube (not executed here) 
                // Run ESLint to analyze code quality for JavaScript/TypeScript, checking for syntax errors, stylistic issues, and potential bugs
                // sh 'npx eslint . --ext .js,.ts'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo "Scanning for potential security risks!"
                echo "Tool: Use Trivy "
                // Example command for Snyk (not executed here)
                //  Use Trivy to scan the local filesystem for known vulnerabilities
                // sh 'trivy fs .'
            }
            post {
                success {
                    mail to: "chinsovatanakvichea@gmail.com",
                        subject: "Security Scan",
                        body: "Security scan successful."
                }
                failure{
                    mail to: "chinsovatanakvichea@gmail.com",
                        subject: "Security Scan",
                        body: "Security scan failed"
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo "Deploying to staging"
                echo "Tool: Custom deployment script (e.g., deploy-script.sh)"
                // Example command for deployment (not executed here)
                // sh 'deploy-script.sh staging'
            }
        }
        
        stage('Integration Test on Staging') {
            steps {
                echo "Integration testing on staging"
                echo "Tool: Custom integration test script (e.g., integration-tests.sh)"
                // Example command for integration testing (not executed here)
                // Run integration tests on the staging environment to ensure the application functions as expected."
                // sh 'integration-tests.sh'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploying to production"
                echo "Tool: Custom deployment script."
                // Example command for production deployment (not executed here)
                // Deploy the application to the production server.
                // sh 'deploy-script.sh production'
            }
        }
    }
    
    post {
        success {
            echo "Pipeline completed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
