pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh '${MAVEN_HOME}/bin/mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh '${MAVEN_HOME}/bin/mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                sh "$PWD"
                dir('D:\Jenkins\Java\jenkins-example')
                withMaven(maven : 'maven_3_6_3') {
                    sh '${MAVEN_HOME}/bin/mvn deploy'
                }
            }
        }
    }
}