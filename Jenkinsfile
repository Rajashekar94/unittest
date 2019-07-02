

node {
    def app
   
    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
   stage('Build') {
      
        sh 'mvn -B -DskipTests clean package'
      
	}
}

