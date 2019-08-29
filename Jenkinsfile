pipeline {
  agent any

  tools {
   maven 'Maven 3.5.2'
        jdk 'Java 9'
  }

    stage('Build') {
      steps {
        sh 'mvn package'
      }
    }
    
    stage('Make Container') {
      steps {
      sh "docker build -t snscaimito/ledger-service:${env.BUILD_ID} ."
      sh "docker tag snscaimito/ledger-service:${env.BUILD_ID} snscaimito/ledger-service:latest"
      }
    }
	 stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
            dockerImage.push()
        }
    }



 
   
}
