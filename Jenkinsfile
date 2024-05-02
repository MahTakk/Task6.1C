pipeline {
    agent any
    stages {
        stage('Build') {
            steps { 
                echo "Using automation tool to build the code"
                echo "Maval is the automation tool used."
            }
         }
        stage('The unit and integaration tests') {
            steps {
                echo "Running unit tests and integration tests to ensure code functionality"
                echo "JUnit is used for unit tests whil Selenium is used for integration tests"
            }
            post {
                success {
                    emailext(
                        to: "maheengulk@gmail.com",
                        subject: "sucess of security scan",
                        body: "The security scan is a success, congratulations",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "maheengulk@gmail.com",
                        subject: "FAILURE of security scan",
                        body: "The security scan failed, try again or make necessary changes",
                        attachLog: true 
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Ensuring industry standrads are met by code analysis"
                echo "SonarQube is the tool used"
            }
        }
        stage ('Security Scan') {
            steps {
                echo "Identifying any vulnerabilities by performing a security scan"
                echo "OWSAP ZAP is the tool used"
            }
            post {
            success {
                emailext(
                to: "maheengulk@gmail.com",
                subject: "SUCCESS of security scan",
                body: "The security scan is a sucess, congratulations",
                attachLog: true
                )
            }
            failure {
                emailext(
                to: "maheengulk@gmail.com",
                subject: "FAILURE of security scan", 
                body: "the security scan failed, try again or make necessary changes",
                attachLog: true 
                )
            }
        }
    }
        stage('Deploy to staging') {
            steps {
                echo "Deploying application to staging server"
                echo "Docker with AWS EC2 is the tool used" 
            }
        }
        stage ('Integration tests on staging') {
            steps {
                echo "Using the statging enviroment to run the integration tests"
                echo "Postman is the tool I used"
            }
        }
        stage('Deploy to production') {
            steps {
                echo "Deploying the application into the production server"
                echo "Kubernetes with AWS EC2 is the tool used" 
            }
        }   
    }
}
