pipeline {
  agent any

  tools {
    maven 'Maven 3.5.2'
  }

  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    
    stage('Make Container') {
      steps {
      sh "docker build -t snscaimito/ledger-service:${env.BUILD_ID} ."
      sh "docker tag snscaimito/ledger-service:${env.BUILD_ID} snscaimito/ledger-service:latest"
      }
    }
}

 
    success {
      withCredentials([usernamePassword(credentialsId: 'docker-credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
        sh "docker login -u ${USERNAME} -p ${PASSWORD}"
        sh "docker push snscaimito/ledger-service:${env.BUILD_ID}"
        sh "docker push snscaimito/ledger-service:latest"
      }
    }
}
