pipeline {
    agent any
    stages {    
    stage('Checkout Code') {
        steps{
    git 'https://github.com/maping/java-maven-calculator-web-app.git'
    }
    }
        
    stage ('JUnit Test') {
        steps {
    if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' clean test"
      } else {
         bat(/"${mvnHome}\bin\mvn" clean test/)
    }
      }
   }
        
   stage('Integration Test') {
       steps {
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' integration-test"
      } else {
         bat(/"${mvnHome}\bin\mvn" integration-test/)
      }
      }
   }
        
 /*
   stage('Performance Test') {
      steps { 
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' cargo:start verify cargo:stop"
      } else {
         bat(/"${mvnHome}\bin\mvn" cargo:start verify cargo:stop/)
         }
      }
   }
  */
        
  stage('Performance Test') {
      steps {
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' verify"
      } else {
         bat(/"${mvnHome}\bin\mvn" verify/)
      }
      }
   }
        
   stage('Deploy') {
       steps {
      timeout(time: 10, unit: 'MINUTES') {
           input message: 'Deploy this web app to production ?'
      }
      echo 'Deploy...'
       }
   }
    }
}
    
    
    
   
   
