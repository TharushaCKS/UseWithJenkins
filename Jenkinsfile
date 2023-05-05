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
            success{
               emailext to:'tharushacao1@gmail.com',
                  subject:"Successfull Security scan by SonarQube",
                  body:"Scan is successfull , please check log"
            }
            failure{
               emailext to:'tharushacao1@gmail.com',
                  subject:"Failed Security scan by SonarQube",
                  body:"Scan is Failed , please check log"
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
         post{
            success{
               emailext to:'tharushacao1@gmail.com',
                  subject:"Successfull Tests scan by TestNG",
                  body:"Test is successfull , please check log"
            }
            failure{
               emailext to:'tharushacao1@gmail.com',
                  subject:"Failed Tests scan by TestNG",
                  body:"Test is Failed , please check log"
            }
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
       emailext to: "tharushacao1@gmail.com",
       subject: "All Passed",
       body: "Please find the attached log file",
       attachLog: true
             }
     failure{
       emailext to: "tharushacao1@gmail.com",
       subject: "Failed ",
       body: "Please find the attached log file",
       attachLog: true
             }
    }

}
}
