node {

  checkout scm
  def dockerImage

  stage('Build image') {
    dockerImage = docker.build("girishsajjanar")
  }

  stage('Push image') {
    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
      dockerImage.push()
    }
  }

}
