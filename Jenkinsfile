node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
stage('compress dist folder')
{
        

sh '''

if [ -f "/unittest/target/" ]
then
   rm -f /unittest/target/
fi

docker run -v $(pwd):/opt maven:3-alpine /bin/bash -c "cd /opt && mvn clean && mvn package &&  mvn install"

'''

        }


}

catch (err) {
    currentBuild.result = "FAILURE"
    throw err
 }
   }

}
