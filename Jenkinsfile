pipeline {

	agent any

    stages {
    
    	stage('Checkout')
    	{
    		steps{
    			git 'https://github.com/tushar30nov/Tushar-spring-petclinic.git'
    		}
    		
    	}
        stage('Build') {   
        
            steps {
             sh "mvn clean package"
            
             echo "Build completed"
            }
            
        }
        stage('Test') {
            steps {
                sh "mvn clean test"
                echo "Test completed"
            }
            
        }
        
        stage('Deploy on Tomcat') {   
        
            steps {
                   
                  sh "cp -R ~/target/spring-petclinic-2.4.5.jar /Users/tusharhadke/Desktop/DevOps/Apache tomcat/apache-tomcat-9.0.46/webapps"
            
            echo "Deployment completed"
            }
            
        }      
   
   }	
       
}
