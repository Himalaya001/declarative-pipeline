pipeline {
  agent any
  stages {
    stage('build') {
      agent any
      environment{
      LOG_LEVEL='INFO'
      }
      steps {
        echo "Building release ${RELEASE} with log_level ${LOG_LEVEL}"
      }
    }
    stage('Test'){
       steps {
        echo "Testing release ${RELEASE}......"
      }
    }
     stage('Deploy'){
       input{
       message='Deploy'
       ok 'Do it !!'
         parameters{
           string(name: 'TARGET_ENVIRONMENT', defaultValue: 'PROD', description: 'Target Deployment Environment')
         }
       }
       steps {
         echo "Deploying ${RELEASE} to environment ${TARGET_ENVIRONMENT}"
      }
    }

  }
   post{
      always{
        echo "Prints whether deploy was successful or failure...."
      }
    }
  environment {
    RELEASE='20.05'
  }
}
