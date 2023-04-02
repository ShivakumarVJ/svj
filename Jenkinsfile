pipeline {
    agent any
    stages {    
        stage('Checkout Code') {
        steps{
            sh '
            git 'https://github.com/ShivakumarVJ/svj.git'
            '
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
        
    
    
   
   
