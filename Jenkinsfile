
node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
stage('Build maven_artifactory'){
  
	sh ' mvn install '
     
	 }
	 }

