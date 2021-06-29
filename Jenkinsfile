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
        
        stage('Deploy') {   
        
            steps {
            sh "mvn clean deploy -U -Dmaven.test.skip=true"
            
            echo "Deployment completed"
            }
            
        }      
   
   }	
       
}
