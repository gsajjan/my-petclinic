pipeline {
  agent any
 stages {
    stage('Build') {
      steps {
        sh 'mvn cliean install -Dmaven.test.skip=true'
      }
    }
 }
}
