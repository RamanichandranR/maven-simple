pipeline {
   agent any
   stages {
     stage('clone') {
         steps {
	   //clone the source code
	   git changelog: false, poll: false, url: 'https://github.com/RamanichandranR/maven-simple.git' 
         }
     }
     stage('build') {
         steps {
	   //build the code
	   mvn clean package
	   echo "code build is done"
	 }
     }
   }
   post {
     always {

	 junit '**/target/surefire-reports/TEST-*.xml'
	 archiveArtifacts 'target/*.jar'
     }
   }
}


