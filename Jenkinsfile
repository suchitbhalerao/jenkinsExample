pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '46542db4-f787-4cb1-9766-281445266df6', url: 'https://github.com/suchitbhalerao/jenkinsExample.git']]])
            }
        }
    }
}
