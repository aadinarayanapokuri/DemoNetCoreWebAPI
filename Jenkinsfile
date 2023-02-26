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
 stage('Build') {  
   steps {  
    bat 'dotnet publish %WORKSPACE%\\DemoNetCoreWebAPI.sln --configuration Release' 
    //bat 'dotnet build C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\HRMPipelines\\jenkins-demo\\HRM\\HRM.sln --configuration Release'  
   }  
  }
stage('Docker') {
    steps {    
     bat "docker build -t aspnetcorewebapi:latest ."    
            }
        }
}
}
