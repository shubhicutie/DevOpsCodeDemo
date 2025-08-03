pipeline{
    
    agent any
    
    tools{
        maven 'mymaven'
    }
    
    stages{
        stage('checkout code')
        {
            steps{
                git  'https://github.com/iam-hemant/DevOpsCodeDemo.git'
            }
        }
        
        stage('Build and Deploy the Code')
        {
            steps{
                sh 'mvn clean install package'
            }
            
            post{

                 success{
                    deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat01', path: '', url: 'http://43.204.115.88:8080/')], contextPath: null, war: '**/*.war'
                }
                
            }
        }
        
    }
    }
