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
         post{
             success {
               echo"Security Scan Successfull"
               emailext to:"tharushacao1@gmail.com",
               subject: "Successfull Security Scan",
               body:"Scan Log attached below",
               attachLog:true
             }
             faliure{
               echo"Security Scan Failed"
               emailext to:"tharushacao1@gmail.com",
               subject: "Failed Security Scan",
               body:"Scan Log attached below",
               attachLog:true
             }
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
        emailext to: "stcao@deakin.edu.au",
        subject: "Build Successfull Email",
        body: "Successfull Stages",
        attachLog:true
    }
    failure {
        emailext to: "stcao@deakin.edu.au",
        subject: "Build Failed Email",
        body: "Failed Stages",
        attachLog:true
    }

   }
}
