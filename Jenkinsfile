pipeline {  
 agent any  
 environment {  
  dotnet = 'C:\\Program Files\\dotnet\\dotnet.exe' 
  DATE = new Date().format('yy.M')
  TAG = "${DATE}.${BUILD_NUMBER}"
   }  
 stages {  
  stage('Checkout') {  
   steps {
       git credentialsId: 'github-cred', url: 'git@github.com:aadinarayanapokuri/DemoNetCoreWebAPI.git', branch: 'main'
   }  
  } 
stage('Docker') {
    steps {    
     bat "docker build -t aspnetcorewebapi:latest ."    
            }
        }
}
}
