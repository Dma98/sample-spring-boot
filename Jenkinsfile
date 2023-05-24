pipeline {
    agent {
        label 'static-slaves'
    }

    tools {
        nodejs 'nodejs'
    }

    triggers {
        githubPush()
    }

    stages {

        stage('Clean') {
            steps {
                cleanWs()
            }

        }
        
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/stoenpav/sample-spring-boot'

            }
        }
        stage('Build') {
            steps {
                sh 'gradlew build'
            }
        }
    }


}