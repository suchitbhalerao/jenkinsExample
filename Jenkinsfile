pipeline {
    agent any
    stages {
      stage('Build') {
        steps {
          sh 'echo "This is my first step"'
        }
     }
      stage('Test') {
        steps {
          sh 'echo "This is my Test step"'
        }
          import groovy.json.JsonSlurper;
            JsonSlurper jsonParser = new JsonSlurper();
            List<Map> jsonMap = (List<Map>)jsonParser.parse(new FileReader("java-config.json"));
            println jsonMap.size();
      }
      stage('Deploy') {
        steps {
          sh 'echo "This is my Deploy step"'
      }
    }
  }
}
