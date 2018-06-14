pipeline {
    agent any

   
    stages {
    
	     stage('checkout') {
	    
	        git 'https://github.com/anoopupadhyay/SeleniumWithCucucumber.git'
	    	
	    	}
	    
	   
	    stage ('Compile Stage') {

            steps {
              
                    sh 'mvn clean compile '
                
            }
        }

		 stage ('Package Stage') {

            steps {
              
                    sh 'mvn package'
                
            }
        }
        stage ('UnitTest Stage') {

            steps {
               
                    sh 'mvn test'
                
            }
        }
		stage ('StaticAnalysis Stage') {
            steps {
               
                    sh 'mvn checkstyle:checkstyle'
                
            }
        }

        stage ('Stg Deployment Stage') {
            steps {
               
                    build job: 'Deploy-to-staging'
                
            }
        }
        stage ('Prod Deployment Prod') {
            steps {
               
                    build job: 'Deploy-to-Prod'
                
            }
        }
    }
}