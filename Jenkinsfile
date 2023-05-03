pipeline {
   agent any
   stages {
      stage('Build') {
         steps {
            // Build the code using Maven
            echo "Maven Compleate
         }
      }
      stage('Unit and Integration Tests') {
         steps {
            // Run unit tests using JUnit
            echo 'mvn test'
            // Run integration tests using Selenium
            echo 'selenium run'
         }
      }
      stage('Code Analysis') {
         steps {
            // Analyze code using SonarQube
            echo 'sonar-scanner'
         }
      }
      stage('Security Scan') {
         steps {
            // Scan code using OWASP ZAP
            echo 'zap-cli quick-scan --spider --scan <target-url>'
         }
      }
      stage('Deploy to Staging') {
         steps {
            // Deploy to staging using AWS CLI
            echo 'aws s3 cp <jar-file> s3://<bucket-name>/<jar-file>'
            echo 'aws ec2 run-instances --image-id <ami-id> --instance-type <instance-type> --count 1'
         }
      }
      stage('Integration Tests on Staging') {
         steps {
            // Run integration tests on staging using Selenium
            echo 'selenium run --staging-url <staging-url>'
         }
      }
      stage('Deploy to Production') {
         steps {
            // Deploy to production using AWS CLI
            echo 'aws s3 cp <jar-file> s3://<bucket-name>/<jar-file>'
            echo 'aws ec2 run-instances --image-id <ami-id> --instance-type <instance-type> --count 1'
         }
      }
   }
   post {
    success {
        mail to: "stcao@deakin.edu.au",
        subject: "Build Successfull Email",
        body: "Successfull"
    }
    failure {
        mail to: "stcao@deakin.edu.au",
        subject: "Build Failed Email",
        body: "Failed"
    }

}
}
