pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = credentials('927d9105-3038-4528-9d30-702c9567645c')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/gcr1991/acr.git']]])
            }
        }


       stage('Build') {
            steps {
                // Use Maven to build the project
                sh "${MAVEN_HOME}/bin/mvn clean install"
            }
        }
    }

    // Post section...
