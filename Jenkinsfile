node {

  checkout scm
  def dockerImage
   tools {
        maven 'Maven 3.5.2'
        jdk 'Java 9'
    }
   stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
   stage ('Build') {
            steps {
                sh 'mvn package'
            }
        }

  stage('Build image') {
     dockerImage = docker.build("girishsajjanar/apche:girish") 
  }

  stage('Push image') {
    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
      dockerImage.push()
    }
  }

}
