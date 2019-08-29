node {

  checkout scm
  def dockerImage

    stage('Build image') {
     dockerImage=docker.image('maven:3.3.3-jdk-8').inside {
 
  sh 'mvn clean package'
}
 
    }
    
    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
            dockerImage.push()
        }
    }

}
