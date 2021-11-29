#!/usr/bin/env groovy
 
/**
        * Sample Jenkinsfile for Jenkins2 Pipeline
        * from https://github.com/hotwilson/jenkins2/edit/master/Jenkinsfile
        * by wilsonmar@gmail.com 
 */
 
import hudson.model.*
import hudson.EnvVars
import groovy.json.JsonSlurperClassic
import groovy.json.JsonBuilder
import groovy.json.JsonOutput
import java.net.URL
import groovy.json.JsonSlurper
 
try {
node {
stage '\u2776 Stage 1'
echo "\u2600 BUILD_URL=${env.BUILD_URL}"
 
def workspace = pwd()
echo "\u2600 workspace=${workspace}"
JsonSlurper jsonParser = new JsonSlurper();
List<Map> jsonMap = (List<Map>)jsonParser.parse(new FileReader("java-config.json")); 
print jsonMap
 
stage '\u2777 Stage 2'
} // node
} // try end
catch (exc) {println exec} finally {
  
 (currentBuild.result != "ABORTED") && node("master") {
     // Send e-mail notifications for failed or unstable builds.
     // currentBuild.result must be non-null for this step to work.
     step([$class: 'Mailer',
        notifyEveryUnstableBuild: true,
        recipients: "suchit.bhalerao@gmail.com",
        sendToIndividuals: true])
 }
 
 // Must re-throw exception to propagate error:
 if (err) {
     throw err
 }
}
