pipeline { 
    agent any  
    stages { 
        stage('Checkout'){

      checkout scm
   }
stage('compress dist folder')
{
        

sh '''

if [ -f "Rajashekar94/unittest/target/" ]
then
   rm -f Rajashekar94/unittest/target/
fi

docker run -v $(pwd)Rajashekar94/unittest/:/opt node:10.15.3-stretch /bin/bash -c "cd /opt && mvn clean && mvn package &&  mvn install"

'''

        }
        
    
 }
		
    }


