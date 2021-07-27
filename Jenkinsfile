pipeline {
    agent any

    tools {
        // Install the Maven version configured as "mymaven" and add it to the path.
        maven "mymaven"
    }

    stages {
        stage('source code checkout') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Debajyoti034/addressbook.git'

            }
        }
        stage('compile') {
            steps {
                sh "mvn compile"
            }
        }    
        stage('review') {
            steps {

                sh "mvn pmd:pmd"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
            
        stage('test') {
            steps {

                sh "mvn test"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
         stage('Package') {
            steps {

                sh "mvn package"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }


        }
  }
}
