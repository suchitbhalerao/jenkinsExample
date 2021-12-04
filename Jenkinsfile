#!/usr/bin/env groovy
 
/**
        * Sample Jenkinsfile for Jenkins2 Pipeline
        * from https://github.com/hotwilson/jenkins2/edit/master/Jenkinsfile
        * by wilsonmar@gmail.com 
 */
 

import groovy.json.JsonSlurper
import jenkins.model.*
   try {
   node {
   stage '\u2776 Stage 1'
   echo "\u2600 BUILD_URL=${env.BUILD_URL}"

   def workspace = pwd()
   echo "\u2600 workspace=${workspace}"
   JsonSlurper jsonParser = new JsonSlurper();
    echo "${env.WORKSPACE}" 
   List<Map> jsonMap = (List<Map>)jsonParser.parse(new FileReader("/var/jenkins_home/workspace/jenkinsExample_main/java-config.json")); 
   print jsonMap

   stage '\u2777 Stage 2'
   } // node
   } // try end
   catch (exc) {println exec} finally {
     print "in finally" 
     }

    // Must re-throw exception to propagate error:
    if (err) {
        throw err
    }

post {
        // Clean after build
        always {
            cleanWs(cleanWhenNotBuilt: false,
                    deleteDirs: true,
                    disableDeferredWipeout: true,
                    notFailBuild: true,
                    patterns: [[pattern: '.gitignore', type: 'INCLUDE'],
                               [pattern: '.propsfile', type: 'EXCLUDE']])
        }
    }
