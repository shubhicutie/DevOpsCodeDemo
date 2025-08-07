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
     deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat01', path: '', url: 'http://43.204.217.65:8080/')], contextPath: null, war: '**/*.war'
    }
  }
}

  
}
