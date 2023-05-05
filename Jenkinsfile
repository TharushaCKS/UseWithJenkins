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
         emailext body: 'The build was successful!',
             subject: 'Build Successful Email',
             to: 'tharushacao1@gmail.com',
             attachmentsPattern: '**/*.log'
               }
      failure {
          emailext body: 'The build failed. Please check the logs for details.',
             subject: 'Build Failed Email',
             to: 'tharushacao1@gmail.com',
             attachmentsPattern: '**/*.log'
               }
   }
}
