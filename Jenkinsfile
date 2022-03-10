pipeline {
    agent any

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
      stage('Post-Build-Actions') {
            steps {
                echo 'triggering another project '
                build 'TestJob2'
            }
        }  
    }
}
