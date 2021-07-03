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
                   
                    deploy adapters: [tomcat9(credentialsId: 'd7d5b225-79c9-4316-a5df-0b81c0752c35', path: '', url: 'http://localhost:8081')], contextPath: 'Users/tusharhadke/Desktop/DevOps/Jenkins Pipeline assignment/spring-petclinic/target', war: 'spring-petclinic-2.4.5.jar'
            
            echo "Deployment completed"
            }
            
        }      
   
   }	
       
}
