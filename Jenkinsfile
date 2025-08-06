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

stage('Deploy Code')
  {
    steps{
      kubernetesDeploy (configs: 'kubedeploy.yml',kubeconfigId: 'k8sconfigpwd')
    }
  }
}

  
}
