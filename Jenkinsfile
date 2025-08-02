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
                    deploy adapters: [tomcat9(credentialsId: 'tomcat01', path: '', url: 'http://35.154.141.110:8080/')], contextPath: null, war: '**/*.war'
                }
                
            }
        }
        
    }
    }
