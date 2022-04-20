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
                    def jsonStr = '{
                      "count": 4,
                      "max": "12",
                      "min": 0,
                      "details": {
                          "REACT_APP_AMAZON_COGNITO_USERPOOL_ID" : \"${REACT_APP_AMAZON_COGNITO_USERPOOL_ID}\",
                          "REACT_APP_AMAZON_COGNITO_CLIENT_ID" : "\"${REACT_APP_AMAZON_COGNITO_CLIENT_ID}\"
                      }
                      }'
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
                   def amap = ['something': 'my datas',
                    'size': 3,
                    'isEmpty': false]    
                     writeJSON file: 'eas.json', json: amap
                     def read = readJSON file: 'eas.json'
               }
           }
       }
   }
}
