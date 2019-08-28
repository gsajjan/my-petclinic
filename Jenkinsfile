node {

  checkout scm
  def dockerImage
    stage('Build') {
            steps {
                sh 'mvn cliean install -Dmaven.test.skip=true'
            }
        }

    stage('Build image') {
     dockerImage = docker.build("girishsajjanar/petclinic:girish") 
    }
    
    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
            dockerImage.push()
        }
    }

}
