pipeline {
    agent any
    stages {    
        stage('Checkout Code') {
        steps{

            git 'https://github.com/ShivakumarVJ/svj.git'
            
        }
        }
        stage ('build') {
        steps {
            sh '
            mvn clean package
                '
        }
    }
    }
        
    
    
   
   
