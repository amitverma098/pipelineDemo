import groovy.json.JsonOutput
import groovy.json.JsonSlurper
pipeline {
   agent { label 'master' }
   environment {
      REACT_APP_AMAZON_COGNITO_USERPOOL_ID = "ca-central-1_8mKgR6sxB"
      REACT_APP_AMAZON_COGNITO_CLIENT_ID = "101"
      REACT_APP_API_KEY = "202"
      REACT_APP_API_URL = "303"
      REACT_APP_MAINTENANCE_MODE = "404"
      REACT_APP_PARSE_URL = "http://helloworld.com"
      REACT_APP_PARSE_APP_ID = "andjsanfjk"
      REACT_APP_PARSE_CLIENT_KEY = "dasnklfnn"
   }
   stages {
       stage('read') {
           steps {
               script {
                   def data = readFile(file: 'zorg.txt')
                   println(data)
               }
           }
       }
       stage('writeToJson'){
           steps {
                  script {
//                    def data = [
//                          name: "${REACT_APP_AMAZON_COGNITO_USERPOOL_ID}",
//                          year: "2018",
//                          timestamp: "2018-03-08T00:00:00",
//                          tags: [ "person", "employee"],
//                          grade: 3.14,
//                       another : [ name : "tim" ,month : "${REACT_APP_AMAZON_COGNITO_CLIENT_ID}"]
//                      ]  
                     
                      def data = [
                         cli: ">= 0.38.3",
                         build: [development: [node: "14.15.0", developmentClient: false, releaseChannel:"development", distribution: "internal", env:[REACT_APP_AMAZON_COGNITO_USERPOOL_ID:"${REACT_APP_AMAZON_COGNITO_USERPOOL_ID}",REACT_APP_AMAZON_COGNITO_CLIENT_ID: "${REACT_APP_AMAZON_COGNITO_CLIENT_ID}",REACT_APP_API_KEY:"${REACT_APP_API_KEY}",REACT_APP_API_URL:"${REACT_APP_API_URL}",REACT_APP_MAINTENANCE_MODE:"${REACT_APP_MAINTENANCE_MODE}",REACT_APP_PARSE_URL:"${REACT_APP_PARSE_URL}",REACT_APP_PARSE_APP_ID:"${REACT_APP_PARSE_APP_ID}",REACT_APP_PARSE_CLIENT_KEY:"${REACT_APP_PARSE_CLIENT_KEY}",WEBSITES3BUCKET:"${WEBSITES3BUCKET}" ] ],preview: [android: [buildType: "apk"],ios:[simulator: true],distribution:"internal"],production:[releaseChannel:"live",ios:[autoIncrement:"version"]]],                         submit:[development:{}] 
                          ] 
                     def json_beauty = JsonOutput.prettyPrint(JsonOutput.toJson(data))
                     writeJSON file: 'eas.json', json: json_beauty
                     def read = readJSON file: 'eas.json'
               }
           }
       }
   }
}
