pipeline {
   agent any
   stages {
      stage('Build') {
         steps {
            // Build the code
            echo "Build Using Maven"
         }
      }
      stage('Unit and Integration Tests') {
         steps {
            // Run unit tests 
            echo ' testing Integration Using Mockito'
         }
         post{
             success {
               echo"Testing is Successfull"
               emailext to:"tharushacao1@gmail.com",
               subject: "Successfull Testing Using Mockito",
               body:"Testing Log attached below",
               attachLog:true
             }
             failure{
               echo"Testing is Failed"
               emailext to:"tharushacao1@gmail.com",
               subject: "Failed Testing Using Mockito",
               body:"Testing Log attached below",
               attachLog:true
             }
         }
      }
      stage('Code Analysis') {
         steps {
        
            echo 'Analyzing code using FindBugs'
         }
      }
      stage('Security Scan') {
         steps {

            echo 'Scanning Security Using OWASP ZAP'
         }
         post{
             success {
               echo"Security Scan Successfull"
               emailext to:"tharushacao1@gmail.com",
               subject: "Successfull Security Scan Using OWASP ZAP",
               body:"Scan Log attached below",
               attachLog:true
             }
             failure{
               echo"Security Scan Failed"
               emailext to:"tharushacao1@gmail.com",
               subject: "Failed Security Scan Using OWASP ZAP",
               body:"Scan Log attached below",
               attachLog:true
             }
         }
      }
      stage('Deploy to Staging') {
         steps {
            // Deploy
            echo 'Deploy Compleate to staging using AWS CodeDeploy'

         }
      }
      stage('Integration Tests on Staging using Selenium ') {
         steps {

            echo 'Tests on Staging compleate'
         }
         post{
             success {
               echo"Testing on Staging Enviroment is Successfull"
               emailext to:"tharushacao1@gmail.com",
               subject: "Successfull Testing (Integration) using Selenium",
               body:"Testing Log attached below",
               attachLog:true
             }
             failure{
               echo"Testing on Staging Enviroment is Failed"
               emailext to:"tharushacao1@gmail.com",
               subject: "Failed Testing Using using Selenium",
               body:"Testing Log attached below",
               attachLog:true
             }
         }
      }
      stage('Deploy to Production') {
         steps {
            // Deploy to production
            echo 'Deploying to Production Using AWS CodeDeploy'
         }
      }
   }
}
