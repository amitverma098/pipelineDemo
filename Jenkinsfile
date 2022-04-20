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
                  const data = [[{"id": "ransomware", "count": 409}, {"id": "phishing", "count": 358}, {"id": "apt", "count": 296}, {"id": "trojans", "count": 180}, {"id": "viruses", "count": 111}, {"id": "backdoors", "count": 99}, {"id": "dos", "count": 97}, {"id": "social engineering", "count": 72}, {"id": "insider threat", "count": 71}, {"id": "payloads", "count": 65}], [{"id": "cve-2019-19781", "count": 15}, {"id": "cve-2019-0708", "count": 14}, {"id": "cve-2020-0601", "count": 9}, {"id": "cve-2020-0674", "count": 8}, {"id": "cve-2019-1182", "count": 8}, {"id": "cve-2019-1181", "count": 8}, {"id": "cve-2019-11510", "count": 7}, {"id": "cve-2019-1367", "count": 7}, {"id": "cve-2020-0796", "count": 6}, {"id": "cve-2019-1429", "count": 6}], [{"id": "banking", "count": 171}, {"id": "retail", "count": 73}, {"id": "military", "count": 67}, {"id": "education", "count": 44}, {"id": "insurance", "count": 38}, {"id": "energy", "count": 36}, {"id": "transport", "count": 29}, {"id": "health care", "count": 29}, {"id": "finance", "count": 22}, {"id": "telcos", "count": 21}], [{"id": "emotet", "count": 61}, {"id": "trickbot", "count": 51}, {"id": "ryuk", "count": 41}, {"id": "bluekeep", "count": 40}, {"id": "wannacry", "count": 35}, {"id": "rover", "count": 18}, {"id": "dridex", "count": 15}, {"id": "azorult", "count": 13}, {"id": "epic", "count": 12}, {"id": "wiper", "count": 11}]]
   
                     writeJSON file: 'eas.json', json: data
                     def read = readJSON file: 'eas.json'
               }
           }
       }
   }
}
