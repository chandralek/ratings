pipeline {

  agent {
    label 'SLAVE'
  }

  environment {
    NEXUS=credentials('Nexus')
    MAJOR_VERSION="1.0"
  }
  stages {


    stage('Create Archive to Upload') {
      steps {
        sh '''
          cd html
          tar -czf ratings-service-${MAJOR_VERSION}-${BUILD_NUMBER}.tgz API.class.php api.php composer.json info.php
        '''
      }
    }

    stage('Upload To Nexus') {
      steps {
        sh '''
          curl -f -v -u $NEXUS --upload-file html/ratings-service-${MAJOR_VERSION}-${BUILD_NUMBER}.tgz https://nexus.devopsb46.online/repository/ratings-service/ratings-service-${MAJOR_VERSION}-${BUILD_NUMBER}.tgz
        '''
      }
    }

  }
}