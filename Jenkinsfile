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
       stage('write') {
           steps {
               script {
                    def jsonStr = '''{
                      "count": 4,
                      "max": "12",
                      "min": 0,
                      "details": {
                          "REACT_APP_AMAZON_COGNITO_USERPOOL_ID" : \"${REACT_APP_AMAZON_COGNITO_USERPOOL_ID}\",
                          "REACT_APP_AMAZON_COGNITO_CLIENT_ID" : "\"${REACT_APP_AMAZON_COGNITO_CLIENT_ID}\"
                      }
                      }'''
                   writeFile(file: 'zorg.txt', text: jsonStr)
                   sh "ls -l"
               }
           }
       }
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
                   import groovy.json.JsonOutput
                   def data = [
                         name: "Foo Bar",
                         year: "2018",
                         timestamp: "2018-03-08T00:00:00",
                         tags: [ "person", "employee"],
                         grade: 3.14
                     ]  
                     def json_beauty = JsonOutput.prettyPrint(JsonOutput.toJson(data))
                     writeJSON file: 'eas.json', json: json_beauty
                     def read = readJSON file: 'eas.json'
               }
           }
       }
   }
}
