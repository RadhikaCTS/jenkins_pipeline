pipeline {
    node Slave2

    stages {
        stage ('Compile Stage') {
            
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
