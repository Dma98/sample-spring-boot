pipeline {
    agent {
        label 'static-slaves'
    }

    tools {
        gradle 'gradle-default'
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
                sh 'gradle build'
            }
        }
    }


}