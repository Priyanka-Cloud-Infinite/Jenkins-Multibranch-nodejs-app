pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'npm install' 
        }
     }
     
     stage('Test') { 
        when{
           expression{
                    env.BRANCH_NAME == 'stage' || env.BRANCH_NAME == 'master'
                    params.ExecuteTest == true
                }
          }
        steps { 
           sh 'echo "testing application..."'
        }
      }

         stage("Deploy nodejs application") { 
         steps { 
           sh 'echo "deploying application..."'
         }
      }
  
    }
    post {
        always{
            echo "always" 
        }
        success{
            echo "sucsess" 
        }
        failure{
            echo "always fails" 
        }
    }
}
