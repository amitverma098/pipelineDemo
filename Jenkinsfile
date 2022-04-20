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
       stage('write') {
           steps {
               script {
                    def jsonStr = '''{
                                     "Orders": [{
                                             "OrderID": \"${REACT_APP_AMAZON_COGNITO_CLIENT_ID}\",
                                             "Customer": \"${REACT_APP_AMAZON_COGNITO_USERPOOL_ID}\",
                                             "Country": "UK",
                                             "Items": [{
                                                     "ProductID": "P07",
                                                     "UnitPrice": 120,
                                                     "Quantity": 10,
                                                     "Variants": [{
                                                             "Color": "Green",
                                                             "Quantity": 4
                                                         }, {
                                                             "Color": "Yellow",
                                                             "Quantity": 6
                                                         }
                                                     ]
                                                 }
                                             ]
                                         }, {
                                             "OrderID": 2502,
                                             "Customer": "Bob",
                                             "Country": "UK",
                                             "Items": [{
                                                     "ProductID": "P05",
                                                     "UnitPrice": 50,
                                                     "Quantity": 5,
                                                     "Variants": [{
                                                             "Color": "Blue",
                                                             "Quantity": 2
                                                         }, {
                                                             "Color": "Red",
                                                             "Quantity": 3
                                                         }
                                                     ]
                                                 }, {
                                                     "ProductID": "P06",
                                                     "UnitPrice": 80,
                                                     "Quantity": 1,
                                                     "Variants": [{
                                                             "Color": "Yellow",
                                                             "Quantity": 1
                                                         }
                                                     ]
                                                 }
                                             ]
                                         }, {
                                             "OrderID": 2501,
                                             "Customer": "Alex",
                                             "Country": "USA",
                                             "Items": [{
                                                     "ProductID": "P05",
                                                     "UnitPrice": 50,
                                                     "Quantity": 1,
                                                     "Variants": [{
                                                             "Color": "Blue",
                                                             "Quantity": 1
                                                         }
                                                     ]
                                                 }
                                             ]
                                         }
                                     ]
                                 }'''
                  def json_beauty = JsonOutput.prettyPrint(JsonOutput.toJson(jsonStr))
                   writeFile(file: 'zorg.txt', text: json_beauty)
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
