pipeline {
   agent { label 'master' }
   environment {
   REACT_APP_AMAZON_COGNITO_USERPOOL_ID = "ca-central-1_8mKgR6sxB"
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
                  def amap = ['REACT_APP_AMAZON_COGNITO_USERPOOL_ID': "${REACT_APP_AMAZON_COGNITO_USERPOOL_ID}",
                    'size': 3,
                    'isEmpty': false]
                     writeJSON file: 'data.json', json: amap
                     def read = readJSON file: 'data.json'
               }
           }
       }
   }
}
