node {

  checkout scm
  def dockerImage

  stage('Build image') {
    dockerImage = docker build -t girishsajjanar/petclinic:build . 
  }

  stage('Push image') {
    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
      dockerImage.push()
    }
  }

}
