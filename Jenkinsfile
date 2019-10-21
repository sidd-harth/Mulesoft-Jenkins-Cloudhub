pipeline{
 agent any
 
 stages {
   stage('Check Parameters') {
   steps {
    echo "Production App Name - ${username}"
    echo "Application Name - ${password}"

   }
  }
 	stage ('Build'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				sh 'mvn -f pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven: 'apache-maven-3.3.9'){
 				sh 'mvn -f pom.xml package deploy  -Dusername=mule-7 -Dpassword=Qwerty67 -DmuleDeploy'
 			}
 		}
 	}
 }

}
