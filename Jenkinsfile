pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo "Tool used: Maven"
                echo "Compiling source code..."
                echo "Packaging application..."
            }
        }
        stage('Unit and Integration Tests'){
            steps{
                echo "Tool used: JUnit"
                echo "Unit testing..."
                echo "Integration testing..."
            }
            post {
                success{
                  mail to: "tobiasjduffy@gmail.com",
                  subject: "Test Status Email",
                  body: "Test was successful!"
            }
                failure{
                  mail to: "tobiasjduffy@gmail.com",
                  subject: "Test Status Email",
                  body: "Test failed."
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo "Tool used: OWASP Dependency-Check"
                echo "Analysing code..."
            }
        }
        stage('Security Scan'){
            steps{
                echo "Tool used: SonarQube"
                echo "Scanning for vulnerabilities..."
            }
            post {
                success{
                  mail to: "tobiasjduffy@gmail.com",
                  subject: "Security Scan Status Email",
                  body: "Scan was successful!"
            }
                failure{
                  mail to: "tobiasjduffy@gmail.com",
                  subject: "Security Scan Status Email",
                  body: "Scan failed."
                }
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo "Tool used: AWS EC2 Instance"
                echo "Deploying to staging server..."
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo "Tool used: Selenium"
                echo "Integration testing"
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Tool used: AWS EC2 Instance"
                echo "Deploying to production..."
            }
        }
    }

}
