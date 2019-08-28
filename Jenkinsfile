node {
	 stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
      }  

	stage('Compile-Package'){
	 def mvnHome = tool name: 'maven', type: 'maven'
	 sh "${mvnHome}/bin/mvn package"
	}
}
