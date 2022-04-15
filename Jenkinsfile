pipeline {
    agent any
    environment {
                REACT_NATIVE_VERSION ="2.2.1"
                REACT_NATIVE_API_URL ="https://obspj4zekh.execute-api.ca-central-1.amazonaws.com/Stgn/v1/"
                REACT_NATIVE_SENTRY_DSN ="https://b1d3d91f43cc41eda5a06a5408a36296@o515346.ingest.sentry.io/5669135"
                REACT_NATIVE_API_HOST ="obspj4zekh.execute-api.ca-central-1.amazonaws.com"
                REACT_NATIVE_API_KEY = "H3huW2srMd2gBiSLc4YCS1y2mCZA7Rlb8xpaRcX1"
                REACT_NATIVE_AUTH_TRIGGER_BYPASS ="WxYhd896hK%$j*hG!"
                REACT_NATIVE_SENSIBILL_API_URL ="https://receipts-sandbox.sensibill.io/api/v1/"
                REACT_NATIVE_SENSIBILL_CLIENT_ID ="ayapaymentsstaging"
                SENTRY_ORG ="aya-care"
                SENTRY_PROJECT ="ayacare-mobile-v2"
                SENTRY_AUTH_TOKEN ="e4814f400b10491dbf675cf6db1a980b054527eddcaf40d9867a3b632ddb1292"

	      
            }

    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
      stage('Test') {
            steps {
                echo 'testing'
            }
        }
      stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        } 
     stage ('writeFileToJson') {
	     steps {
                echo 'writing'
		        script {
          def someMap = [
              'name' : "john",
              'surname' : "doe"
          ]
          def json = new groovy.json.JsonBuilder()
          json "people": someMap
          def file = new File("$WORKSPACE/people.json")
          file.write(groovy.json.JsonOutput.prettyPrint(json.toString()))
        }
            }   
        }  
    }
}
