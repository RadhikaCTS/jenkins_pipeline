pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn clean compile'
                }
            }
        }
        
            
        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn test'
                }
            }
        }
        
                
        stage ('Build on Slave Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn package'
                }
            }
        }
        
        
              
        
        
        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn install'
                }
            }
        }
    }
}
