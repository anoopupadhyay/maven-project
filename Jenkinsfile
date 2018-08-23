pipeline {
    agent any
tools {
   maven 'apache-maven-3.5.4'
  }
   
    stages {
    
	    stage ('Compile Stage') {

            steps {
              
                    sh 'mvn clean'
                
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
