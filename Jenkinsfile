

node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
stage('Build maven_artifactory'){

    def mvn_version = 'M3'
withEnv( ["PATH+MAVEN=${/home/ubuntu/installations/apache-maven-3.6.1}/bin"] ) {
  sh "mvn clean package"
}
	
}
}

