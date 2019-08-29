node(‘linux’){
  git url: 'https://github.com/gsajjan/my-petclinic.git'
  def mvnHome = tool 'M3'
  env.PATH = "${mvnHome}/bin:${env.PATH}"
  sh 'mvn -B clean verify'
}
