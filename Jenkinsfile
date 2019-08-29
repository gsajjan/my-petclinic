node {

  checkout scm
  def dockerImage

    stage('Build image') {
     dockerImage=docker.image('maven:3.3.3-jdk-8').inside {
  git 'https://github.com/gsajjan/my-petclinic.git'
  sh 'mvn -B clean install'
}
 
    }
    
    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
            dockerImage.push()
        }
    }

}
