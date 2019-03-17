pipeline {
    agent Slave2

    stages {agent { label 'Slave2' }
        stage ('Compile Stage') {
            agent { label 'Slave2' }
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Package Test') {
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn package'
            }
          }
        }

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn install'
                }
            }
        }
    }
}
