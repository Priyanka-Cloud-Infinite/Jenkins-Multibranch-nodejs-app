pipeline { 
  
   agent any

   stages {
     stage('Install Dependencies') { 
        steps { 
           sh 'npm install' 
        }
      }
      stage('Test') { 
        steps { 
           sh 'echo "testing application..."'
        }
      }
      stage("Deploy application") { 
         steps { 
           sh 'echo "deploying application..."'
         }
     }
  
  } 
  post {
        always {
            echo 'Test run completed'
        }
        success {
            echo 'Successfully!'
        }
        failure {
            echo 'Failed!'
        }
    }
}
