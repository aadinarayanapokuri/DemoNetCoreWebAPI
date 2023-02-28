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
       git credentialsId: 'github-jenkins', url: 'git@github.com:aadinarayanapokuri/DemoNetCoreWebAPI.git', branch: 'main'
   }  
  } 
stage('Docker') {
    steps {    
     sh "docker build -t aspnetcorewebapi:latest ."    
            }
        }
stage('image push to ECR') {
    steps {    
     sh "aws ecr get-login-password --region ap-northeast-1 | docker login --username AWS --password-stdin 670166063118.dkr.ecr.ap-northeast-1.amazonaws.com"    
            }
        }
}
}
