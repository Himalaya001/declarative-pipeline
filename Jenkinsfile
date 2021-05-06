pipeline {
  agent any
  stages {
    stage('build') {
      agent any
      environment{
      LOG_LEVEL='INFO'
      }
      steps {
        echo 'Building release ${RELEASE} with log_level ${LOG_LEVEL}'
      }
    }
    stage('Test'){
       steps {
        echo 'Testing release ${RELEASE} but log_level ${LOG_LEVEL} is not visible'
      }
    }

  }
  environment {
    RELEASE='20.05'
  }
}
