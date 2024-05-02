pipeline {
    agent any
    stages {
        stage('Build') {
            steps { 
                echo "Using automation tool to build the code"
                echo "Blue Ocean is the automation tool used."
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
                echo "Checkmarx is the tool used"
            }
        }
        stage ('Security Scan') {
            steps {
                echo "Identifying any vulnerabilities by performing a security scan"
                echo "Burp Suite is the tool used"
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
                echo "ECS is the tool used" 
            }
        }
        stage ('Integration tests on staging') {
            steps {
                echo "Using the statging enviroment to run the integration tests"
                echo "Insomnia Core is the tool I used"
            }
        }
        stage('Deploy to production') {
            steps {
                echo "Deploying the application into the production server"
                echo "Kops is the tool used" 
            }
        }   
    }
}
