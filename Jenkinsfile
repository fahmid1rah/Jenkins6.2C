pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using MAVEN automation tool to compile and package the code.'
            }
        }
        stag('Unit and Integration Test') {
            steps {
                echo 'Unit Test - Unit tests ensures the code functions as expected using JUNIT.'
                echo 'Integration Test - Integration tests ensures the different components of the application work together as expected using SELENIUM.'
            }
            post{
                success{
                    mail to: "fahmid1rah@gmail.com",
                    subject: "Unit and Integration Test Status Email",
                    body: "This Unit and Integration Test is successful. The console log output for the current deployment is in the following link: ${BUILD_URL}/consoleText" 
                    
                }
                failure{
                    mail to: "fahmid1rah@gmail.com",
                    subject: "Unit and Integration Test Status Email",
                    body: "This Unit and Integration Test is unsuccessful. The console log output for the current deployment is in the following link: ${BUILD_URL}/consoleText"
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Code Analysis is done using COVERITY.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'The code is scanned using QUALYS  to identify any vulnerabilities'
            }
            post{
                success{
                    mail to: "fahmid1rah@gmail.com",
                    subject: "Security Scan Status Email",
                    body: "This Security Scan is successful. The console log output for the current deployment is in the following link: ${BUILD_URL}/consoleText"
                }
                failure{
                    mail to: "fahmid1rah@gmail.com",
                    subject: "Security Scan Status Email",
                    body: "This Security Scan is unsuccessful. The console log output for the current deployment is in the following link: ${BUILD_URL}/consoleText"
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deployed to staging environment AWS EC2.'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration tests for staging environment done using SELENIUM.'
            }
            post{
                success{
                    mail to: "fahmid1rah@gmail.com",
                    subject: "Integration Tests on Staging Status Email",
                    body: "This Integration Tests on Staging is successful. The console log output for the current deployment is in the following link: ${BUILD_URL}/consoleText"
                }
                failure{
                    mail to: "fahmid1rah@gmail.com",
                    subject: "Integration Tests on Staging Status Email",
                    body: "This Integration Tests on Staging is unsuccessful. The console log output for the current deployment is in the following link: ${BUILD_URL}/consoleText"
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'The code is deployed to the production environment AWS EC2.'
            }
        }
    }
}
