pipeline {
   agent any
   stages {
      stage('Build') {
         steps {
            // Build the code
            echo "Build Compleate"
         }
      }
      stage('Unit and Integration Tests') {
         steps {
            // Run unit tests 
            echo ' testing Integration '
         }
      }
      stage('Code Analysis') {
         steps {
        
            echo 'Analyzing code'
         }
      }
      stage('Security Scan') {
         steps {

            echo 'Scanning Security'
         }
      }
      stage('Deploy to Staging') {
         steps {
            // Deploy
            echo 'Deploy Compleate to staging'

         }
      }
      stage('Integration Tests on Staging') {
         steps {

            echo 'Tests on Staging compleate'
         }
      }
      stage('Deploy to Production') {
         steps {
            // Deploy to production
            echo 'Production Deployment Compleate'
         }
      }
   }
   post {
    success {
      // Send an email notification with logs on successful build and deployment
      emailext body: "The build and deployment process was successful. Please find attached the logs.", to: 'email@example.com', subject: 'Build and deployment successful', attachmentsPattern: '*.log'
    }
    failure {
      // Send an email notification with logs on failed build and deployment
      emailext body: "The build and deployment process failed. Please find attached the logs.", to: 'email@example.com', subject: 'Build and deployment failed', attachmentsPattern: '*.log'
    }
}
}
