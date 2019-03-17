pipeline {
    node (Slave2)

    stages {agent { label 'slave-node​' }
        stage ('Compile Stage') {
            agent { label 'slave-node​' }
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
