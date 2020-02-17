
pipeline {
    agent any

    stages {
        stage ('Checking java version') {

            steps {
             
                    sh 'java -version'
         
            }
        }

        stage ('exporting maven Environment variable') {

            steps {
             
                    sh 'export M2_HOME=/opt/maven'
                    sh 'export M2_HOME=/opt/maven'
                
            }
        }


        stage ('maven version') {
            steps {
               
                    sh 'mvn -version'
                
            }
        }

        stage ('Building APP') {
            steps {
               
                    sh 'mvn clean package'
                
            }
        }


	stage ('REST') {
            steps {
     
                    sh 'sleep 10'

            }
        }

        stage ('Building docker image') {
            steps {
               
                    sh 'sudo docker build -t dock .'
                
            }
        }

	stage ('Again rest') {
            steps {

                    sh 'sleep 10'

            }
        }
	stage ('Pushing docker image to registry') {
            steps {

                    sh 'sudo docker tag  dock:latest maventest:1.0 && sudo docker push maventest:1.0'            }
        }


    }


}
