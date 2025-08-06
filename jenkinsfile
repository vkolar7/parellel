pipeline{
  agent none;
  stages {
    stage ('BUILD'){
      agent { label 'Java_Build' }
      steps {
        echo " Build is done "
        sh 'sleep 5'
        }
      }
    stage ('TEST') {
      parallel {
        stage ('TEST_C') {
          agent { label 'Test_C' }
          steps {
            echo " Testing C build "
            sh 'sleep 5'
          }
        }
        stage ('TEST_JAVA') {
          agent { label 'Test_Java' }
          steps {
            echo " Testing Java Build"
            sh 'sleep 5'
          }
        }
      }
    }
    stage ('DEPLOY') {
      agent { label 'Java_Build' }
      steps {
        echo " Deploying Build to Production "
        sh 'sleep 5'
      }
    }
  }
}
