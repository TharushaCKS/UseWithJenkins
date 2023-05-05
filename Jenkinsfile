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
    success{
       echo "Security Scan succesful"
       emailext to: "jesvinsabu3@gmail.com",
       subject: "Security Sacn Successfull",
       body: "Please find the attached log file",
       attachLog: true
             }
     failure{
       echo "Security Scan Failed"
       emailext to: "jesvinsabu3@gmail.com",
       subject: "Security Scan Failed",
        body: "Please find the attached log file",
        attachLog: true
             }
    }

}
