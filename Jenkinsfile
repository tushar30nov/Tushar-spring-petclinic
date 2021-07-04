pipeline {

	agent any

    stages {
    
    	stage('Checkout')
    	{
    		steps{
    			git 'https://github.com/tushar30nov/Tushar-spring-petclinic.git'
    		}
    		
    	}
             stage('Test') {
            steps {
                sh "mvn clean test"
                echo "Test completed"
            }
            
        stage('Build') {   
        
            steps {
             sh "mvn package"
            
             echo "Build completed"
                    
                    
            }
           
        }
       
        }
        
        stage('Deploy on Tomcat') {   
        
            steps {
                   
                  sh "java -jar target/spring-petclinic-2.4.5.jar --server.port=8082"
            
            echo "Deployment completed"
            }
            
        }      
   
   }	
       
}
