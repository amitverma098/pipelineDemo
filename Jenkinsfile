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
                   def date = new Date()
                   def data = "Hello World\nSecond line\n" + date
                   writeFile(file: 'zorg.txt', text: data)
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
            def jsonStr = '''{
               "count": 4,
               "max": "12",
               "min": 0,
               "details": [{
               "goBus": {
               "first": 12800,
               "second": 11900,
               "third": 12800
               },
               "goAir": {
               "first": 12800,
               "second": 11900,
               "third": 12800
               },
               "gotTrain": {
               "first": 12800,
               "second": 11900,
               "third": 12800,
               "fourth": 13000
               },
               "sell": true,
               "darn": 2,
               "rate": [{
               "busRate": 11900,
               "flag": false,
               "percent": 0
            }]
            }]
            }'''
                     writeJSON file: 'eas.json', json: jsonStr
                     def read = readJSON file: 'eas.json'
               }
           }
       }
   }
}
