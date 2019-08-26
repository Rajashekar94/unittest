node {
  
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
     }
    stage('Build maven_artifactory'){
        
        sh "mvn install"
    }
    
   stage('email') {
       emailext body: 'this is test email', subject: 'test-email', to: 'rajashekaryadav470@gmail.com'
    
      }
   }








//this is the original file
//node {
  //  def app

    //stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

      //  checkout scm
    //}
//stage('Build maven_artifactory'){
//     sh "mvn install"
//}
//}
