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
       git credentialsId: '159cc590-911a-4367-a1f6-491df39982a2', url: 'https://github.com/ramudammu/DemoNetCoreWebAPI1.git', branch: 'main'
   }  
  } 
 stage('Build') {  
   steps {  
    bat 'dotnet publish %WORKSPACE%\\DemoNetCoreWebAPI.sln --configuration Release' 
    //bat 'dotnet build C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\HRMPipelines\\jenkins-demo\\HRM\\HRM.sln --configuration Release'  
   }  
  }
stage('Docker Build') {
            steps {
                script {
                    docker.build("ramudammu/aspnetcorewebapi:${TAG}")
                }
            }
        }
}
}
