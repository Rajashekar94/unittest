

node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
stage('Build maven_artifactory'){

  withEnv( ["PATH+MAVEN=${/home/ubuntu/installations/apache-maven-3.6.1}/bin"] ) {
  sh "mvn clean package"
}
	
}
}

