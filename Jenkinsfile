pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
              
                    sh 'mvn clean compile '
                
            }
        }

		 stage ('package Stage') {

            steps {
              
                    sh 'mvn package'
                
            }
        }
        stage ('Unit Stage') {

            steps {
               
                    sh 'mvn test'
                
            }
        }
		stage ('Static Test') {
            steps {
               
                    sh 'mvn checkstyle:checkstyle'
                
            }
        }

        stage ('Deployment Stage') {
            steps {
               
                    build job: 'Deploy-to-staging'
                
            }
        }
        stage ('Deployment Prod') {
            steps {
               
                    build job: 'Deploy-to-Prod'
                
            }
        }
    }
}