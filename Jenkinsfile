pipeline{
agent any
  tools{
     maven 'mymaven'
  }

stages{
stage('clone Repo')
  {
    steps{
       git branch: 'master', url: 'https://github.com/iam-hemant/DevOpsCodeDemo.git'
     
    }
  }
stage('Build Code')
  {
    steps{
       sh 'mvn package'   
    }
  }

stage('Deploy Code in tomcat')
  {
    steps{
     deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatcred02', path: '', url: 'http://13.126.253.187:8080/')], contextPath: null, war: '**/*.war'
   }
  }
}

  
}
