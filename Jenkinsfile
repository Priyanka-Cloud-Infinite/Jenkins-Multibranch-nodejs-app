pipeline {  
  
   agent any
    parameters{
        choice(name:'VERSION',choices :['1.1.0','1.2.0','1.3.0'])
        booleanParam(name:'ExecuteTest',defaultValue:true,description:'')
    }
   stages {
     stage('Install Dependencies') { 
        steps { 
           sh 'npm install' 
        }
      }
      stage('Test') {
        when{
                expression{
                    env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'master' || env.BRANCH_NAME=='stage'
                    params.ExecuteTest == true
                }
            }
        steps { 
           sh 'echo "testing application..."'
        }
      }
      stage("Deploy application") { 
         steps { 
           sh 'echo "deploying application..."'
           echo "deploying version ${params.VERSION}"
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
