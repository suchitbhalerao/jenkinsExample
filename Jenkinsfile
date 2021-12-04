pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                        echo 'Building..'
                        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '46542db4-f787-4cb1-9766-281445266df6', url: 'https://github.com/suchitbhalerao/jenkinsExample.git']]])
                        def props = readJSON file: 'java-config.json'
                        echo 'java component is: ' props['java-component']
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
