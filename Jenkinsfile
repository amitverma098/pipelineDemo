pipeline {
   agent { label 'master' }
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
                    def amap = ['something': 'my datas',
                    'size': 3,
                    'isEmpty': false]
                     writeJSON file: 'data.json', json: amap
                     def read = readJSON file: 'data.json'

                     assert read.something == 'my datas'
                     assert read.size == 3
                     assert read.isEmpty == false
               }
           }
       }
   }
}
