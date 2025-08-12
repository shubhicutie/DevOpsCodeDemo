
pipeline{
    tools{
       
        maven 'mymaven'
    }
	agent any
      stages{
           stage('Checkout the code'){
	    
               steps{
		 echo 'cloning the repo'
                 git 'https://github.com/shubhicutie/DevOpsCodeDemo.git'
              }
          }
          stage('Compile'){
             
              steps{
                  echo 'complie the code again..'
                  sh 'mvn compile'
	      }
          }
          stage('CodeReview'){
		  
              steps{
		    
		  echo 'codeReview'
                  sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
		  
              steps{
	         
                  sh 'mvn test'
              }
          
          }
        
          stage('Package'){
		  
              steps{
		  
                  sh 'mvn package'
              }
          }

	stage('Deploy Code in tomcat')
  {
    steps{
     deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat01', path: '', url: 'http://13.126.253.187:8080/')], contextPath: null, war: '**/*.war'
   }
  }
	  }
 }
