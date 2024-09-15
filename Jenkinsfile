pipeline {
    agent any 
    stages {
        stage("Build") {
            steps {
                echo "Build the code using a build automation tool to compile and package your code."
                echo "Maven is a popular tool used for Java-based build automation that can handle dependency management, compilation, packaging, and testing."
                echo "Gradle can become useful if you want to handle diverse languages."
            }
        }
        stage("Unit and Integration Tests") {
            steps {
                echo "Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected."
                echo "JUnit is the popular Java framework used for unit testing and integration."
                echo "If you are looking for something for web development, Selenium can be useful."
            }
        }
        stage("Code Analysis") {
            steps {
                echo "Integrate a code analysis tool to analyze the code and ensure it meets industry standards."
                echo "SonarQube can be useful in this case for continuous inspection of code quality and security."
            }
        }
        stage("Security Scan") {
            steps {
                echo "Perform a security scan on the code using a tool to identify any vulnerabilities."
                echo "ZAP (Zed Attack Proxy) is a popular open-source web application security scanner."
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        to: "chinsovatanakvichea@gmail.com",
                        subject: "Build Status Email",
                        body: "The file is safe to use.",
                        
                    )
                }
                failure {
                    emailext(
                        attachLog: true,
                        to: "chinsovatanakvichea@gmail.com",
                        subject: "Build Status Email",
                        body: "Security issues found in the files presented.",
                    )
                }
            }
        }
        stage("Deploy to Staging") {
            steps {
                echo "Deploy the application to a staging server."
                echo "Azure CLI is a command-line interface for Azure services, allowing deployment to Azure infrastructure."
            }
        }
        stage("Integration Tests on Staging") {
            steps {
                echo "Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment."
                echo "Tools like JUnit and Selenium are again used after staging."
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        to: "chinsovatanakvichea@gmail.com",
                        subject: "Build Status Email",
                        body: "Integration was successful.",
                    )
                }
                failure {
                    emailext(
                        attachLog: true,
                        to: "chinsovatanakvichea@gmail.com",
                        subject: "Build Status Email",
                        body: "Integration was unsuccessful and something didn't work as expected.",
                    )
                }
            }
        }
        stage("Deploy to Production") {
            steps {
                echo "Deploy the application to a production server."
                echo "Azure is also used in this stage. Aside from that, AWS and Ansible can also be used."
            }
        }
    }
}
